/**
 * game url : http://zzzscore.com/1to50/en/
 * paste code in console , and happy to hack
 */
var Hacker = function () {
    var self = this;
    self.now_click_number = 1;

    function getNextBox() {
        if (self.now_click_number > 50) {
            return;
        }
        var box_list = $('#grid div');
        for (var i in box_list) {
            var box = box_list[i];
            if (parseInt(box.textContent) === self.now_click_number) {
                clickBox($(box));
                return;
            }
        }
    }

    function clickBox(box) {
        box.trigger('tap');
        self.now_click_number += 1;
        setTimeout(getNextBox,100);
    }
    
    getNextBox();
}

new Hacker();
