

<template>
  <div class="red-content">
    <div class="red-package-top">
      <div class="red-package-top-box">
        <em>￥</em>
        <span>5</span>
      </div>
    </div>
    <div class="red-package-text"><img src="../assets/images/red-package-text.png"></div>
    <div class="red-package-erweima"><img src="../assets/images/red-package-erweima.jpg"></div>
    <div class="red-package-yqm">
      <em>102589</em>
    </div>
    <div class="red-package-download">
      <a href="#"><img src="../assets/images/red-package-download.jpg"></a>
    </div>
    <div class="red-package-tips"><img src="../assets/images/red-package-tips.jpg"></div>
  </div>
</template>
<script>
export default {
  mounted() {
    $(document).ready(function() {
      var length = $(".red-package-top span").text().length;
      if (length == 1) {
        $(".red-package-top span").css({
          "margin-top": "2rem",
          "font-size": "3rem"
        });
      }
      if (length == 2) {
        $(".red-package-top span").css({
          "margin-top": "2.5rem",
          "font-size": "2.2rem"
        });
      }
      if (length == 3) {
        $(".red-package-top span").css({
          "margin-top": "2.7rem",
          "font-size": "1.8rem"
        });
      }
    });

    !(function(win) {
      function resize() {
        var domWidth = domEle.getBoundingClientRect().width;
        if (domWidth / v > 750) {
          domWidth = 750 * v;
        }
        win.rem = domWidth / 16;
        domEle.style.fontSize = win.rem + "px";
      }
      var v,
        initial_scale,
        timeCode,
        dom = win.document,
        domEle = dom.documentElement,
        viewport = dom.querySelector('meta[name="viewport"]'),
        flexible = dom.querySelector('meta[name="flexible"]');
      if (viewport) {
        var o = viewport
          .getAttribute("content")
          .match(/initial\-scale=(["']?)([\d\.]+)\1?/);
        if (o) {
          initial_scale = parseFloat(o[2]);
          v = parseInt(1 / initial_scale);
        }
      } else if (flexible) {
        var o = flexible
          .getAttribute("content")
          .match(/initial\-dpr=(["']?)([\d\.]+)\1?/);
        if (o) {
          v = parseFloat(o[2]);
          initial_scale = parseFloat((1 / v).toFixed(2));
        }
      }
      if (!v && !initial_scale) {
        var n = (win.navigator.appVersion.match(/android/gi),
        win.navigator.appVersion.match(/iphone/gi));
        v = win.devicePixelRatio;
        (v = n ? (v >= 3 ? 3 : v >= 2 ? 2 : 1) : 1), (initial_scale = 1 / v);
      }
      //没有viewport标签的情况下
      if ((domEle.setAttribute("data-dpr", v), !viewport)) {
        if (
          ((viewport = dom.createElement("meta")),
          viewport.setAttribute("name", "viewport"),
          viewport.setAttribute(
            "content",
            "initial-scale=" +
              initial_scale +
              ", maximum-scale=" +
              initial_scale +
              ", minimum-scale=" +
              initial_scale +
              ", user-scalable=no"
          ),
          domEle.firstElementChild)
        ) {
          domEle.firstElementChild.appendChild(viewport);
        } else {
          var m = dom.createElement("div");
          m.appendChild(viewport), dom.write(m.innerHTML);
        }
      }
      win.dpr = v;
      win.addEventListener(
        "resize",
        function() {
          clearTimeout(timeCode), (timeCode = setTimeout(resize, 300));
        },
        false
      );
      win.addEventListener(
        "pageshow",
        function(b) {
          b.persisted &&
            (clearTimeout(timeCode), (timeCode = setTimeout(resize, 300)));
        },
        false
      );
      resize();
    })(window);
  }
};
</script>

<style scoped>
html,
body {
  height: 100%;
  background-color: #ce3a37;
}
.red-content {
  max-width: 750px;
  padding-bottom: 1.1rem;
}
.red-package-top {
  width: 100%;
  height: 17.6rem;
  margin: 0 auto;
  overflow: hidden;
  font-size: 0;
  text-align: center;
  background-image: url("../assets/images/red-package-top.png");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  margin-bottom: 0.5rem;
}
.red-package-top-box {
  width: 10.625rem;
  height: 10.55rem;
  margin: 0 auto;
  position: relative;
  background-image: url("../assets/images/red-package-top-box.png");
  background-position: center center;
  background-repeat: no-repeat;
  background-size: 100% 100%;
  margin-top: 2.95rem;
  text-align: center;
}
.red-package-top em {
  position: absolute;
  left: 38%;
  top: 2.2rem;
  font-size: 0.75rem;
  color: #ce3a37;
  font-weight: 700;
}
.red-package-top span {
  margin-top: 2.5rem;
  display: inline-block;
  color: #ce3a37;
  font-weight: 700;
}
.red-package-text,
.red-package-text img {
  width: 14rem;
  height: 6rem;
  margin: 0 auto;
}
.red-package-erweima,
.red-package-erweima img {
  height: 7.625rem;
  width: 7.625rem;
  margin: 1.25rem auto;
}
.red-package-yqm {
  width: 9.55rem;
  height: 1.85rem;
  font-size: 0;
  padding-left: 5rem;
  text-align: left;
  margin: 0 auto 0.7rem;
  background-color: #fff;
  background-image: url("../assets/images/red-package-yqm.jpg");
  background-position: left center;
  background-repeat: no-repeat;
  background-size: 4.7rem 100%;
}
.red-package-yqm em {
  display: inline-block;
  line-height: 2rem;
  font-size: 1rem;
  color: #ce3a37;
  font-weight: bolder;
}
.red-package-download {
  width: 9.55rem;
  height: 1.475rem;
  margin: 0 auto 1.1rem;
}
.red-package-tips {
  width: 13.25rem;
  height: 5.65rem;
  margin: 0 auto;
}
</style>
