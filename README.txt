
TITLE: 
cognifyiqb2b- 100% Fully Responsive Free HTML5 Bootstrap Template

AUTHOR:
DESIGNED & DEVELOPED by GetTemplates.co

Website: http://gettemplates.co/
Twitter: http://twitter.com/gettemplatesco
Facebook: http://facebook.com/gettemplatesco


CREDITS:

Bootstrap
http://getbootstrap.com/

jQuery
http://jquery.com/

jQuery Easing
http://gsgd.co.uk/sandbox/jquery/easing/

Modernizr
http://modernizr.com/

Google Fonts
https://www.google.com/fonts/

Icomoon
https://icomoon.io/app/

Respond JS
https://github.com/scottjehl/Respond/blob/master/LICENSE-MIT

animate.css
http://daneden.me/animate

jQuery Waypoint
https://github.com/imakewebthings/waypoints/blog/master/licenses.txt

Owl Carousel
http://www.owlcarousel.owlgraphic.com/

jQuery countTo
http://www.owlcarousel.owlgraphic.com/

Magnific Popup
http://dimsemenov.com/plugins/magnific-popup/

Demo Images:
http://unsplash.com

const modal = $("#a2a_modal", context);
  const openButton = $(".a2a_dd", context); // the button that opens the Share modal

  // Trap focus inside modal
  function trapFocus(element) {
    const focusableEls = element.find(
      'a[href], area[href], input:not([disabled]), select:not([disabled]), textarea:not([disabled]), button:not([disabled]), [tabindex]:not([tabindex="-1"])'
    );
    const firstFocusableEl = focusableEls[0];
    const lastFocusableEl = focusableEls[focusableEls.length - 1];

    element.on("keydown", function (e) {
      if (e.key !== "Tab") return;

      if (e.shiftKey) {
        // Shift + Tab
        if (document.activeElement === firstFocusableEl) {
          e.preventDefault();
          $(lastFocusableEl).focus();
        }
      } else {
        // Tab
        if (document.activeElement === lastFocusableEl) {
          e.preventDefault();
          $(firstFocusableEl).focus();
        }
      }
    });
  }

  // Move focus inside modal when opened
  openButton.on("click", function () {
    setTimeout(() => {
      const firstFocusable = modal.find(
        "button, [href], input, select, textarea, [tabindex]:not([tabindex='-1'])"
      ).first();

      if (firstFocusable.length) {
        firstFocusable.focus();
      } else {
        modal.attr("tabindex", "-1").focus();
      }

      trapFocus(modal);
    }, 300);
  });

  // Close modal on ESC key and return focus to opener
  $(document).on("keydown", function (e) {
    if (e.key === "Escape") {
      if (modal.is(":visible")) {
        modal.hide();
        openButton.focus();
      }
    }
  });
}


