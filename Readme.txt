<html>
  <head>
    <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-entity id="cameraRig">
        <a-camera></a-camera>
      </a-entity>
    </a-scene>

    <script>
      if (window.DeviceMotionEvent) {
        window.addEventListener("devicemotion", function (event) {
          let acceleration = event.accelerationIncludingGravity;
          let cameraRig = document.querySelector("#cameraRig");

          if (acceleration.x > 1 || acceleration.y > 1) {
            cameraRig.object3D.position.z -= 0.1; // Movimiento hacia adelante
          }
        });
      }
    </script>
  </body>
</html>
