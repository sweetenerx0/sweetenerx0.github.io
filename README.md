<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Dani's Website</title>
  <style>
    /* Page styling */
    html, body {
      height: 100%;
      margin: 0;
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background-color: #FFC0CB; /* baby pink */
      color: #222;
    }

    /* Centered header */
    header {
      padding: 48px 16px;
      text-align: center;
    }
    header h1 {
      margin: 0;
      font-size: 28px;
      line-height: 1.2;
      font-weight: 600;
    }

    /* Main content area */
    main {
      max-width: 900px;
      margin: 24px auto;
      padding: 0 16px;
    }

    /* Image area */
    .image-box {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      margin: 20px 0;
    }
    .image-box img {
      max-width: 100%;
      height: auto;
      border-radius: 8px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    }

    /* Small helper styles */
    label.file-label {
      background: #fff;
      padding: 8px 12px;
      border-radius: 6px;
      cursor: pointer;
      box-shadow: 0 2px 6px rgba(0,0,0,0.06);
    }
    input[type="file"] {
      display: none;
    }

    p {
      font-size: 16px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Hi. This is Dani's Website. Thank you for visiting !</h1>
  </header>

  <main>
    <!-- Image upload & preview area -->
    <section class="image-box" aria-label="Image upload and preview">
      <!-- Static image you can replace -->
      <img id="preview" src="path/to/your-image.jpg" alt="Your image here" />
      <!-- Or choose a file from your computer to preview -->
      <label for="imageInput" class="file-label">Choose an image to preview</label>
      <input id="imageInput" type="file" accept="image/*" />
      <small>If you do not select a file, the static image path above will be shown (replace the src).</small>
    </section>

    <!-- Body paragraph -->
    <p>test</p>
  </main>

  <script>
    // Simple image preview: when user selects a file, show it in the <img id="preview">
    const input = document.getElementById('imageInput');
    const preview = document.getElementById('preview');

    input.addEventListener('change', () => {
      const file = input.files && input.files[0];
      if (!file) return;

      const reader = new FileReader();
      reader.onload = (e) => {
        preview.src = e.target.result;
        preview.alt = file.name;
      };
      reader.readAsDataURL(file);
    });
  </script>
</body>
</html>
