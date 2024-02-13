### [Stirling-PDF](https://github.com/Frooodle/Stirling-PDF)

#### Install using Git

If you are a git user, you can install the theme and keep up to date by cloning the repo:

```bash
git clone https://github.com/dracula/stirling-pdf.git
```

#### Install manually

Download using the [GitHub `.zip` download](https://github.com/dracula/stirling-pdf/archive/main.zip) option and unzip them.

#### Activating theme

If you don't have Stirling-PDF installed, you can do so with the following `docker-compose.yaml`:

```yaml
version: "3.3"
services:
  stirling-pdf:
    image: frooodle/s-pdf:latest
    ports:
      - "8080:8080"
    volumes:
      - /path/to/data/directory:/usr/share/tesseract-ocr/5/tessdata #Required for extra OCR languages
      - /path/to/configs/directory:/configs
      - /path/to/customFiles/directory:/customFiles/
      - /path/to/logs/directory:/logs/
    environment:
      - DOCKER_ENABLE_SECURITY=false # Set to true to enable basic auth
      - SECURITY_ENABLE_LOGIN=false # Optional: If DOCKER_ENABLE_SECURITY is true, set this to true to enable login screen
```

1. First, create a `static` directory in your `/path/to/configs/directory`. Inside that `static` directory, create a directory called `css`.
2. Inside that `css` directory (ex: `/path/to/configs/directory/static/css`), create a `css` file called `dark-mode.css`.
3. Inside your `dark-mode.css` file in your `/path/to/configs/directory/static/css`, paste the contents of [dark-mode](dark-mode.css) and save the file to apply the theme.

   This is what you directory structure should look like if your `/path/to/configs/directory` is something like `/home/bob/MyContainers/StirlingPDF/custom_files`:

   ```
   home
   ├── bob
   |   ├── MyContainers
   |   |   ├── StirlingPDF
   |   |   |   ├── custom_files
   |   |   |   |   ├── static
   |   |   |   |   |   ├── css
   |   |   |   |   |   |   ├── dark-mode.css
   ```

4. Boom! It's working ✨
