// ==UserScript==
// @name              autof5
// @author           𝘯𝘦𝘷𝘦𝘳𝘮𝘰𝘳𝘦𝘦
// @version          1.1
// @description      new

// @match            https://*.test-eu.tankionline.com/browser-public/index.html?*
// @match            https://tankionline.com/play*
// @match            https://*.tankionline.com/*

// @icon             https://i.pinimg.com/564x/8c/e0/54/8ce054c0223e578ad97ee3362072de6e.jpg

// @grant            unsafeWindow
// @grant            GM_xmlhttpRequest
// @run-at           document-start
// ==/UserScript==

(function() {
    'use strict';

    // Функция для имитации нажатия клавиши Enter
    function pressEnterKey() {
        var event = new KeyboardEvent('keydown', {
            key: 'Enter',
            code: 'Enter',
            keyCode: 13,
            charCode: 13,
            bubbles: true
        });
        document.dispatchEvent(event);
    }

    // Установите интервал обновления страницы
    setInterval(function() {
        pressEnterKey(); // Нажимаем Enter перед обновлением
        setTimeout(function() {
            location.reload(); // Обновляем страницу
            setTimeout(function() {
                pressEnterKey(); // Нажимаем Enter после обновления
                setTimeout(function() {
                    pressEnterKey(); // Нажимаем Enter второй раз после обновления
                }, 100); // Ждем 100 мс перед вторым нажатием клавиши
            }, 100); // Ждем 200 мс перед первым нажатием клавиши после обновления
        }, 100); // Ждем 200 мс перед обновлением
    }, 20000); // 20000 миллисекунд = 20 секунд

})();
