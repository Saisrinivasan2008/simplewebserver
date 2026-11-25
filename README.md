# EX01 Developing a Simple Webserver
## Date: 25/11/2026
## Name: T.S.Sai Srinivasan
## Department: Btech IT



## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
<!DOCTYPE html>
<html>
<head>
  <title>Laptop Specifications</title>
  <style>
    body { font-family: Arial; margin: 40px; }
    table { border-collapse: collapse; }
    th, td { border: 1px solid black; padding: 8px 16px; text-align: left; }
  </style>
</head>
<body>
  <h2>My Laptop Specifications</h2>
  <table id="specs"></table>

  <script>
    function getGPU() {
      try {
        const gl = document.createElement("canvas").getContext("webgl");
        const info = gl.getExtension("WEBGL_debug_renderer_info");
        return gl.getParameter(info.UNMASKED_RENDERER_WEBGL);
      } catch (e) {
        return "Not available";
      }
    }

    const specs = {
      "Operating System": navigator.platform,
      "CPU Cores": navigator.hardwareConcurrency,
      "RAM (approx.)": navigator.deviceMemory ? navigator.deviceMemory + " GB" : "Not available",
      "Screen Resolution": screen.width + " x " + screen.height,
      "Graphics Card": getGPU(),
      "Browser": navigator.userAgent
    };

    for (const key in specs) {
      document.getElementById("specs").innerHTML +=
        "<tr><th>" + key + "</th><td>" + specs[key] + "</td></tr>";
    }
  </script>
</body>
</html>
## OUTPUT:
<img width="1471" height="398" alt="Screenshot 2026-11-25 174214" src="https://github.com/user-attachments/assets/0c9612cb-1f1b-4853-92d1-304a6e84e63f" />


## RESULT:
The program for implementing simple webserver is executed successfully.
