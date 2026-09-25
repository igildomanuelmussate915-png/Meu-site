document.addEventListener("DOMContentLoaded", () => {
const menuButton = document.getElementById("menuButton");
const mainNav = document.getElementById("mainNav");
const contactButton = document.getElementById("contactButton");
const contactMessage = document.getElementById("contactMessage");
const year = document.getElementById("year");
const navLinks = document.querySelectorAll(".nav a");

const updateMenuButton = (isOpen) => {
    if (menuButton) {
        menuButton.setAttribute("aria-label", isOpen ? "Fechar menu" : "Abrir menu");
        menuButton.textContent = isOpen ? "✕" : "☰";
    }
};

const closeMenu = () => {
    if (mainNav) {
        mainNav.classList.remove("active");
    }

    if (menuButton) {
        updateMenuButton(false);
    }
};

if (menuButton && mainNav) {
    menuButton.addEventListener("click", () => {
        const isOpen = mainNav.classList.toggle("active");
        updateMenuButton(isOpen);
    });
}

if (navLinks) {
    navLinks.forEach((link) => {
        if (link) {
            link.addEventListener("click", closeMenu);
        }
    });
}

if (contactButton && contactMessage) {
    contactButton.addEventListener("click", () => {
        contactMessage.textContent =
            "Obrigado pelo interesse! A área de contacto será configurada em breve.";
    });
}

if (year) {
    year.textContent = new Date().getFullYear();
}

});
