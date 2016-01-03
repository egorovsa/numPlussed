/*
* Plugin is animate number. Begin in 0 and end in 234 or other number.
// HTML
<h4>234</h4>
//JS
* jQuery('h4').numPlussed(); // For init
* jQuery('h4')..numPlussed('animate'); // for animate
*/
(function ($) {
    var methods = {
        init: function (options) {
            this.each(function () {
                var $this = jQuery(this);

                var settings = jQuery.extend({
                }, options);

                $this.data({
                    numPlussed: {
                        settings: settings
                    }
                });
                methods._initCopy($this);
            });
        },
        _initCopy: function ($this) {
            var data = $this.data().numPlussed;
            data.beginNum = $this.text();
        },
        animate: function () {
            var $this = jQuery(this)
            methods.time($this, 0);

        },
        time: function ($this, num) {
            var self = this;
            var data = $this.data().numPlussed;
            var beginNum = data.beginNum;
            var speen = beginNum > 50 ? (beginNum - num) / 4 : 40;
            setTimeout(function () {
                num++;
                $this.text(num);
                if (num < beginNum)
                    self.time($this, num);
            }, speen);
        }
    };
    jQuery.fn.numPlussed = function (method) {
        if (methods[method]) {
            return methods[ method ].apply(this, Array.prototype.slice.call(arguments, 1));
        } else if (typeof method === 'object' || !method) {
            return methods.init.apply(this, arguments);
        }
    };
})(jQuery);
