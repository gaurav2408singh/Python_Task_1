# UI/UX Enhancement for FOSSEE Workshop Booker

This project is a submission for the Python Screening Task. The goal was to take the existing Django-based workshop booking website and improve its user interface and user experience, with a primary focus on mobile responsiveness.

repo: https://github.com/FOSSEE/workshop_booking

---

## Setup and Installation

To run this project locally, please follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Yash0951/Task1.git
    cd Task1
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    # For Windows
    python -m venv env
    .\env\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    pip install setuptools
    ```

4.  **Set up the database:**
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

5.  **Create an admin user:**
    ```bash
    python manage.py createsuperuser
    ```
    *(Follow the prompts to create your admin user)*

6.  **IMPORTANT: Create the user's profile:**
    * Start the server: `python manage.py runserver`
    * Go to the admin panel in your browser: `http://127.0.0.1:8000/admin/`
    * Log in with the admin user you just created.
    * On the admin dashboard, find "Profiles" and click **"+ Add"**.
    * Select your username from the "User" dropdown, fill in any other required details, and click **SAVE**.

7.  **Run the server (for normal use):**
    ```bash
    python manage.py runserver
    ```
    You can now log into the main site at `http://127.0.0.1:8000/workshop/login/`

--


<!-- ## Visual Showcase: Before and After

Here are screenshots demonstrating the UI/UX improvements, particularly in mobile view.

| Before | 
![HOME PAGE](workshop_booking/screenshots/OLD_home.png)
![STATISTICS PAGE](workshop_booking/screenshots/OLD_statistics.png)
![ADMIN PAGE](workshop_booking/screenshots/OLD_admin1.png)
![ADMIN PAGE](workshop_booking/screenshots/OLD_admin2.png)

| improved | 
![HOME PAGE](workshop_booking/screenshots/imroved_home.png)
![HOME PAGE](workshop_booking/screenshots/improved_home2.png)
![STATISTICS](workshop_booking/screenshots/improved_statitics.png)

| new |
![HOME PAGE](workshop_booking/screenshots/NEW_home.png) 
![HOME PAGE](workshop_booking/screenshots/NEW_home.png)
![HOME PAGE](workshop_booking/screenshots/NEW_home2.png)
![LOGIN PAGE](workshop_booking/screenshots/NEW_login.png)
![REGISTER PAGE](workshop_booking/screenshots/NEW_register.png)
![STATISTICS PAGE](workshop_booking/screenshots/NEW_statistics.png)
![STATISTICS PAGE](workshop_booking/screenshots/NEW_statistics2.png)
![STATISTICS PAGE](workshop_booking/screenshots/NEW_statistics3.png)
![ADMIN PAGE](workshop_booking/screenshots/NEW_admin.png)

| mobile view/ responsive|
![MOBILE VIEW](workshop_booking/screenshots/Mobile1.png)
![MOBILE VIEW](workshop_booking/screenshots/Mobile2.png)
![MOBILE VIEW](workshop_booking/screenshots/Mobile3.png)
![MOBILE VIEW](workshop_booking/screenshots/Mobile5.png)
![MOBILE VIEW](workshop_booking/screenshots/Mobile4.png)
![MOBILE VIEW](workshop_booking/screenshots/Mobile6.png)

--- -->

## Visual Showcase: Before and After

Here are screenshots demonstrating the UI/UX improvements, particularly in mobile view.

### Key Page Improvements

| Before | After |
| :---: | :---: |
| ![Old Login Page](screenshots/OLD_home.png) |![New Status Page](screenshots/improved_home2.png) 
| *Original, non-responsive login form.* | *New, responsive login form with a professional layout.* |
| ![Old Statistics Page](screenshots/OLD_statistics.png) | ![New Statistics Page](screenshots/NEW_statistics.png) |
| *Original statistics page with a rigid table.* | *New statistics page with improved filters and layout.* |
| ![Old Status Page](screenshots/OLD_admin1.png) | ![New Login Page](screenshots/NEW_login.png) | |
| *Original workshop status page.* | *New workshop status page using a responsive, card-based grid.* |

---

### Complete Screenshot Gallery

#### Original ("Before") Design
| | | | |
| :---: | :---: | :---: | :---: |
| ![Old Home Page](screenshots/OLD_home.png) | ![Old Statistics Page](screenshots/OLD_statistics.png) | ![Old Admin Page 1](screenshots/OLD_admin1.png) |
| ![Old Admin Page 2](screenshots/OLD_admin2.png) | | |

#### Final ("After") Design
| | | | | |
| :---: | :---: | :---: | :---: | :---: |
| ![New Home Page](screenshots/NEW_home0.png) | ![New Home Page](screenshots/NEW_home.png) |![New Home Page](screenshots/NEW_home2.png) |![New Login Page](screenshots/NEW_login.png) | ![New Register Page](screenshots/NEW_register.png) |
| ![New Statistics Page 1](screenshots/NEW_statistics.png) | ![New Statistics Page 2](screenshots/NEW_statistics2.png) | ![New Statistics Page 3](screenshots/NEW_statistics3.png) |![Admin Page](screenshots/NEW_admin.png) |

#### Mobile Responsive View
| | | |
| :---: | :---: | :---: |
| ![Mobile View 1](screenshots/Mobile1.png) | ![Mobile View 2](screenshots/Mobile2.png) | ![Mobile View 3](screenshots/Mobile3.png) |
| ![Mobile View 4](screenshots/Mobile5.png) | ![Mobile View 5](screenshots/Mobile4.png) | ![Mobile View 6](screenshots/Mobile6.png) |
<!-- ## Reasoning and Design Principles

#### What design principles guided your improvements?

* **Mobile-First Design:** The primary goal was to ensure the interface was clean, readable, and fully functional on small screens. The design was approached from a mobile perspective first.
* **Clarity and Simplicity:** The old, dense tables were replaced with a clean, card-based layout. Whitespace and a clear visual hierarchy were used to reduce clutter and guide the user.
* **Consistency:** A unified color palette and typography were established in a central `custom.css` file. This ensures that all components—navbars, buttons, cards, footers—share a single, professional design language.

#### How did you ensure responsiveness across devices?

* **Bootstrap's Grid System:** The core of the responsiveness relies on Bootstrap's `flexbox`-based grid (`.row`, `.col-lg-4`, etc.). This allows the card layout to automatically reflow from multiple columns on a desktop to a single column on a mobile device.
* **Responsive Components:** Standard Bootstrap components were used, most notably the `navbar`, which now collapses into a hamburger menu on mobile, and `form-control` classes that ensure form inputs stretch to 100% width on phones.
* **Fluid Containers:** Using `.container-fluid` in the navbar and `.container` for content ensures that the layout uses screen space effectively while preventing horizontal overflow.

#### What trade-offs did you make between the design and performance?

* **Framework vs. Pure CSS:** I used the Bootstrap framework to ensure a reliable and fast development cycle. The trade-off is a slightly larger initial file size compared to writing minimal, custom CSS from scratch, but the benefit is robust, pre-tested components.
* **Readability vs. Animations:** The design prioritizes fast load times and a clean, readable interface over complex JavaScript animations, which could harm performance on less powerful mobile devices.

#### What was the most challenging part of the task and how did you approach it?

The most challenging part was integrating the modern Bootstrap form styling with Django's template rendering. Django's default `{{ form.as_p }}` tags don't allow for the necessary CSS classes. The solution was to manually render each form field in the HTML templates (`login.html`, `register.html`, etc.). This provided complete control over the markup, allowing me to add the required Bootstrap classes like `.form-control` and achieve a clean, consistent, and fully responsive design for all forms. -->

##  Reasoning and Design Principles

### What design principles guided your improvements?
I focused on three key principles while improving the design. First, I went with a **mobile-first approach**, making sure the interface looked clean and worked smoothly even on smaller screens. Second, I aimed for **clarity and simplicity**—instead of cluttered tables, I introduced a card-based layout with proper spacing and visual hierarchy so users can quickly find what they need. Lastly, I emphasized **consistency** by defining a unified color palette and typography in a central CSS file. This way, everything—from buttons to navbars—follows the same professional design language.

---

### How did you ensure responsiveness across devices?
The responsiveness is mainly powered by **Bootstrap’s grid system**, which automatically adjusts layouts from multiple columns on desktops to single columns on mobile. I also relied on **responsive components**, like a collapsing navbar that turns into a hamburger menu on smaller screens, and form inputs that stretch to full width on phones. To make sure space is used effectively, I combined **fluid containers** for the navbar with standard containers for content, preventing unnecessary overflow.

---

### What trade-offs did you make between design and performance?
I chose to use **Bootstrap** instead of writing pure custom CSS. While this slightly increases the initial file size, the trade-off is worth it because Bootstrap provides reliable, pre-tested components that speed up development. Another trade-off was prioritizing **readability over heavy animations**. I kept the interface fast and lightweight rather than adding fancy transitions that might slow things down on weaker mobile devices.

---

### What was the most challenging part of the task and how did you approach it?
The toughest part was **styling Django’s forms** with Bootstrap. Django’s default `{{ form.as_p }}` tags don’t allow the flexibility needed to add Bootstrap classes. To solve this, I manually rendered each form field inside the templates (like `login.html` and `register.html`). It was extra work, but it gave me complete control over the markup and let me apply classes like `.form-control`, ensuring all forms looked clean, modern, and consistent across devices.
