// Wait for DOM to be fully loaded
document.addEventListener('DOMContentLoaded', function() {
    
    // Mobile Navigation Toggle
    const hamburger = document.querySelector('.hamburger');
    const navMenu = document.querySelector('.nav-menu');
    
    hamburger.addEventListener('click', function() {
        hamburger.classList.toggle('active');
        navMenu.classList.toggle('active');
    });
    
    // Close mobile menu when clicking a link
    document.querySelectorAll('.nav-link').forEach(n => n.addEventListener('click', () => {
        hamburger.classList.remove('active');
        navMenu.classList.remove('active');
    }));
    
    // Page Navigation System
    const pageLinks = document.querySelectorAll('[data-page]');
    const pageSections = document.querySelectorAll('.page-section');
    const modals = document.querySelectorAll('.modal');
    
    // Function to show a specific page/modal
    function showPage(pageId) {
        // Hide all pages
        pageSections.forEach(section => {
            section.classList.remove('active');
        });
        
        // Remove active class from all nav links
        pageLinks.forEach(link => {
            link.classList.remove('active');
        });
        
        // Show the requested page
        const targetPage = document.getElementById(pageId);
        if (targetPage) {
            targetPage.classList.add('active');
            
            // Add active class to corresponding nav link
            document.querySelector(`[data-page="${pageId}"]`).classList.add('active');
            
            // If it's a modal, make sure body doesn't scroll
            if (targetPage.classList.contains('modal')) {
                document.body.style.overflow = 'hidden';
            } else {
                document.body.style.overflow = 'auto';
            }
        }
    }
    
    // Add click event to all page links
    pageLinks.forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const pageId = this.getAttribute('data-page');
            showPage(pageId);
            
            // Scroll to top when navigating
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
    });
    
    // Close modal functionality
    const closeModalButtons = document.querySelectorAll('.close-modal');
    
    closeModalButtons.forEach(button => {
        button.addEventListener('click', function() {
            // Hide all modals
            modals.forEach(modal => {
                modal.classList.remove('active');
            });
            
            // Show home page
            showPage('home');
            
            // Restore body scroll
            document.body.style.overflow = 'auto';
        });
    });
    
    // Close modal when clicking outside
    modals.forEach(modal => {
        modal.addEventListener('click', function(e) {
            if (e.target === this) {
                // Hide all modals
                modals.forEach(m => {
                    m.classList.remove('active');
                });
                
                // Show home page
                showPage('home');
                
                // Restore body scroll
                document.body.style.overflow = 'auto';
            }
        });
    });
    
    // Tutorial Navigation
    const tutorialLinks = document.querySelectorAll('.tutorial-link, .btn-link[data-tutorial]');
    const tutorialArticles = document.querySelectorAll('.tutorial-article');
    
    tutorialLinks.forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const tutorialId = this.getAttribute('data-tutorial');
            
            // Hide all tutorial articles
            tutorialArticles.forEach(article => {
                article.style.display = 'none';
            });
            
            // Show the selected tutorial
            const targetTutorial = document.getElementById(`tutorial${tutorialId}`);
            if (targetTutorial) {
                targetTutorial.style.display = 'block';
                
                // Update active state in tutorial navigation
                document.querySelectorAll('.tutorial-link').forEach(tl => {
                    tl.classList.remove('active');
                });
                
                document.querySelector(`.tutorial-link[data-tutorial="${tutorialId}"]`).classList.add('active');
                
                // Scroll to the tutorial
                targetTutorial.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }
        });
    });
    
    // CTA Card Hover Animations
    const ctaCards = document.querySelectorAll('.cta-card');
    
    ctaCards.forEach(card => {
        card.addEventListener('mouseenter', function() {
            const animationType = this.getAttribute('data-animate');
            if (animationType === 'pulse') {
                this.style.animation = 'pulse 0.5s';
            }
        });
        
        card.addEventListener('animationend', function() {
            this.style.animation = '';
        });
    });
    
    // Add CSS for pulse animation
    const style = document.createElement('style');
    style.textContent = `
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
    `;
    document.head.appendChild(style);
    
    // Teaser Card Click - Navigate to tutorials
    const teaserCards = document.querySelectorAll('.teaser-card');
    
    teaserCards.forEach(card => {
        card.addEventListener('click', function(e) {
            e.preventDefault();
            const page = this.getAttribute('data-page');
            if (page) {
                showPage(page);
            }
        });
    });
    
    // Smooth scrolling for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            const href = this.getAttribute('href');
            
            // Only handle internal page anchors (not external links)
            if (href.startsWith('#') && href.length > 1) {
                e.preventDefault();
                const targetElement = document.querySelector(href);
                if (targetElement) {
                    targetElement.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            }
        });
    });
    
    // WhatsApp link tracking (optional analytics)
    const whatsappLinks = document.querySelectorAll('a[href*="wa.me"], a[href*="whatsapp"]');
    
    whatsappLinks.forEach(link => {
        link.addEventListener('click', function() {
            const linkType = this.classList.contains('btn-primary') ? 'quote' : 
                           this.classList.contains('btn-secondary') ? 'query' : 
                           this.classList.contains('btn-tertiary') ? 'career' : 'other';
            
            console.log(`WhatsApp link clicked: ${linkType}`);
            // Here you could add actual analytics tracking
        });
    });
    
    // Initialize first tutorial as visible
    if (document.getElementById('tutorial1')) {
        document.getElementById('tutorial1').style.display = 'block';
    }
    
    // Add some interactive animations to cartoon elements
    const cartoonElements = document.querySelectorAll('.cartoon-character, .celebration-character');
    
    cartoonElements.forEach((element, index) => {
        // Add slight delay for staggered animation
        element.style.animationDelay = `${index * 0.1}s`;
        element.style.animation = `float 3s ease-in-out infinite`;
    });
    
    // Add floating animation
    const floatStyle = document.createElement('style');
    floatStyle.textContent = `
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    `;
    document.head.appendChild(floatStyle);
    
    // Handle browser back button for modal navigation
    window.addEventListener('popstate', function() {
        // If a modal is open, close it and return to home
        const openModal = document.querySelector('.modal.active');
        if (openModal) {
            openModal.classList.remove('active');
            showPage('home');
            document.body.style.overflow = 'auto';
        }
    });
    
    // Add active state to clicked nav links for better UX
    document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', function() {
            // Update URL without reloading (for UX)
            const page = this.getAttribute('data-page');
            history.pushState(null, '', `#${page}`);
        });
    });
    
    // Check URL hash on load
    if (window.location.hash) {
        const pageId = window.location.hash.substring(1);
        if (document.getElementById(pageId)) {
            showPage(pageId);
        }
    }
});
