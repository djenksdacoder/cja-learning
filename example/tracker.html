// Tracker.js - External Script for Multi-Page Analytics
(function() {
    const CONFIG = {
        siteId: 'scanner-site-123', // Customize per page if needed (e.g., 'report-site-456')
        storageKey: 'scannerAnalyticsData' // Shared across all pages in folder
    };

    // Global queue (GA-style)
    window.analyticsTracker = window.analyticsTracker || function() { this.q = []; return this.push.apply(this, arguments); };
    const queue = window.analyticsTracker.q = [];

    // Load data (for sync, but mainly append)
    let dataStore = JSON.parse(localStorage.getItem(CONFIG.storageKey)) || [];

    // Build event params – WITH PAGE CONTEXT
    function getParams(type = 'pageview') {
        const pagePath = window.location.pathname;
        const pageFile = pagePath.split('/').pop() || 'index.html'; // e.g., 'scanner.html'
        return {
            siteId: CONFIG.siteId,
            type: type,
            pageFile: pageFile, // For easy slicing (filename)
            pageUrl: pagePath, // Full relative URL
            url: window.location.href, // Legacy full URL
            referrer: document.referrer || '',
            userAgent: navigator.userAgent,
            language: navigator.language,
            screen: `${screen.width}x${screen.height}`,
            timestamp: new Date().toISOString()
        };
    }

    // Store event locally
    function storeData(eventData) {
        const fullEvent = { ...eventData, receivedAt: new Date().toISOString() };
        dataStore.push(fullEvent);
        localStorage.setItem(CONFIG.storageKey, JSON.stringify(dataStore));
        console.log('Tracked:', fullEvent); // Debug – now includes pageFile
    }

    // Command handler (for manual calls if needed)
    function command(...args) {
        queue.push(args);
        const [cmd, type, extra] = args;
        if (cmd === 'track') {
            const params = { ...getParams(type), ...extra };
            storeData(params);
        }
    }

    // Expose global API (e.g., for custom events)
    window.trackEvent = command;

    // Auto-capture all button clicks + text
    function setupButtonTracking() {
        document.addEventListener('click', function(e) {
            const button = e.target.closest('button, input[type="button"]');
            if (button) {
                const buttonText = button.textContent.trim() || button.alt || button.getAttribute('aria-label') || 'Unnamed Button';
                storeData({
                    ...getParams('button_click'),
                    buttonText: buttonText,
                    buttonId: button.id || 'no-id'
                });
            }
        }, true); // Use capture phase for perf
    }

    // Auto-track pageview + setup buttons
    function initTracker() {
        storeData(getParams('pageview'));
        if (document.readyState === 'loading') {
            document.addEventListener('DOMContentLoaded', setupButtonTracking);
        } else {
            setupButtonTracking();
        }
    }

    initTracker();
})();
