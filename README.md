<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<br />
<div align="center">
  <h3 align="center">StockMaster</h3>

  <p align="center">
    A Django + PostgreSQL inventory management system with role-based dashboards, supplier and
    sales tracking, low-stock reporting and audit logs.
    <br />
    <a href="https://github.com/Elouahabi-Naoufal/inventory-management-system"><strong>Explore the source »</strong></a>
    <br />
    <br />
    <a href="https://github.com/Elouahabi-Naoufal/inventory-management-system/issues/new?labels=bug">Report Bug</a>
    &middot;
    <a href="https://github.com/Elouahabi-Naoufal/inventory-management-system/issues/new?labels=enhancement">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

StockMaster is a PFM project from the 3rd year of EMSI. It is a server-rendered Django application
using PostgreSQL, built around three roles: **admin**, **staff** and **supplier**. Each role gets
a different dashboard and a different set of permitted operations.

Implemented functionality includes:

* Product and stock management with add, edit and delete
* Sales, purchases and supplier purchases that update stock levels and account balances
* Customer records and purchase history
* Supplier and staff profiles
* Low-stock indicators and an inventory statistics dashboard
* Monthly reports with CSV export
* Activity logging, analytics and user administration
* Support tickets with responses and priority/status tracking
* A balance/wallet view for supplier transactions

The UI is rendered with Django templates and a small amount of JavaScript.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

* [![Django][Django]][Django-url]
* [![Python][Python]][Python-url]
* [![PostgreSQL][PostgreSQL]][PostgreSQL-url]
* [![HTML5][HTML5]][HTML5-url]
* [![CSS3][CSS3]][CSS3-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

* Python 3.10+
* PostgreSQL
* pip and a virtual environment
* Django 5.2 and a PostgreSQL driver (`psycopg2` / `psycopg2-binary`)

There is no `requirements.txt` in the repository, so the Python dependencies are not pinned.

### Installation

1. Clone the repository
   ```sh
   git clone https://github.com/Elouahabi-Naoufal/inventory-management-system.git
   cd inventory-management-system/inventory_web
   ```

2. Create and activate a virtual environment
   ```sh
   python3 -m venv env
   source env/bin/activate
   ```

3. Install Django and the PostgreSQL driver
   ```sh
   pip install "Django>=5.2" psycopg2-binary
   ```

4. Create the database
   ```sh
   psql -U postgres -c 'CREATE DATABASE inventory;'
   ```
   The committed settings connect as `postgres` / `0000` on `localhost:5432`. Edit
   `inventory_web/settings.py` if your credentials differ.

5. Apply migrations
   ```sh
   python manage.py migrate
   ```

6. Create an administrator
   ```sh
   python manage.py createsuperuser
   ```

7. Start the development server
   ```sh
   python manage.py runserver
   ```

8. Open <http://127.0.0.1:8000/>

Optional sample data:

* `python create_users.py` creates 20 suppliers and 10 staff accounts (password `inventory12`).
* `products.sql` contains a set of sample products. It expects a supplier with id `2`, so load it
  after creating that account.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

1. Sign in at `/accounts/login/`, or create a staff/supplier account at `/accounts/signup/`.
2. Use `/inventory/` to add and manage products.
3. Record a sale or purchase from `/transactions/`; stock and balances update automatically.
4. Review low-stock items and totals on `/` and `/analytics/`.
5. Export monthly reports as CSV from `/reports/`.
6. Administrators can inspect `/activity-log/` and manage users through the analytics screens.
7. Suppliers see their own products and transactions; staff see the operational views.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [x] Role-based dashboards for admin, staff and supplier accounts
- [x] Product, stock, customer, supplier and transaction management
- [x] CSV report export and activity logging
- [x] Support tickets and analytics
- [ ] Add a pinned `requirements.txt`
- [ ] Move database credentials and `SECRET_KEY` to environment variables
- [ ] Add automated tests for the transaction and balance logic
- [ ] Add a repeatable seed command covering users, suppliers and products

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire,
and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Top contributors:

<a href="https://github.com/Elouahabi-Naoufal/inventory-management-system/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Elouahabi-Naoufal/inventory-management-system" alt="contrib.rocks image" />
</a>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

This project is not licensed — all rights reserved.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Naoufal Elouahabi - [LinkedIn](https://www.linkedin.com/in/elouahabi-naoufal/) - elouahabi-naoufal1@gmail.com

Project Link: [https://github.com/Elouahabi-Naoufal/inventory-management-system](https://github.com/Elouahabi-Naoufal/inventory-management-system)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

* [Django documentation](https://docs.djangoproject.com/)
* [PostgreSQL documentation](https://www.postgresql.org/docs/)
* [Best-README-Template](https://github.com/othneildrew/Best-README-Template)
* [Img Shields](https://shields.io)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/Elouahabi-Naoufal/inventory-management-system.svg?style=for-the-badge
[contributors-url]: https://github.com/Elouahabi-Naoufal/inventory-management-system/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Elouahabi-Naoufal/inventory-management-system.svg?style=for-the-badge
[forks-url]: https://github.com/Elouahabi-Naoufal/inventory-management-system/network/members
[stars-shield]: https://img.shields.io/github/stars/Elouahabi-Naoufal/inventory-management-system.svg?style=for-the-badge
[stars-url]: https://github.com/Elouahabi-Naoufal/inventory-management-system/stargazers
[issues-shield]: https://img.shields.io/github/issues/Elouahabi-Naoufal/inventory-management-system.svg?style=for-the-badge
[issues-url]: https://github.com/Elouahabi-Naoufal/inventory-management-system/issues
[license-shield]: https://img.shields.io/badge/license-none-lightgrey?style=for-the-badge
[license-url]: #license
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/elouahabi-naoufal/
[Django]: https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white
[Django-url]: https://www.djangoproject.com/
[Python]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[Python-url]: https://www.python.org/
[PostgreSQL]: https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white
[PostgreSQL-url]: https://www.postgresql.org/
[HTML5]: https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
[HTML5-url]: https://developer.mozilla.org/docs/Web/HTML
[CSS3]: https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white
[CSS3-url]: https://developer.mozilla.org/docs/Web/CSS
