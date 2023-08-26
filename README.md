# FTP File Uploader Tool

## Overview

The FTP File Uploader is a lightweight and efficient tool designed to simplify the process of uploading files to an FTP server. Specifically, it targets the `htdocs` directory of a website. Once the file is uploaded, the tool provides the HTTP-based URL to access the uploaded file directly from the server. This tool is especially useful for those who frequently upload files and want to avoid the hassle of using traditional FTP clients and manually converting filenames into URLs.

## Features

- **Simple UI**: Easily select and upload files with just a few clicks.
- **.netrc Integration**: Automatically fetches credentials from the `.netrc` file, eliminating the need to manually input them each time.
- **Instant URL Generation**: After the file is uploaded, get the direct HTTP URL to access it.
- **Secure**: Uses TLS for FTP connections.

## Prerequisites

- Tcl/Tk installed on your system.
- Required Tcl packages: `http`, `tls`, and `ftp`.
- A `.netrc` file set up with the credentials of the FTP server(s) you wish to connect to.

## Setup

1. Ensure you have Tcl/Tk installed on your system.
2. Clone this repository or download the tool.
3. Make sure the script has execute permissions. You can set it with: `chmod +x <script_name>.tcl`
4. Run the script: `./<script_name>.tcl`

## Usage

1. Launch the FTP File Uploader tool.
2. From the dropdown list, select the desired FTP server (as configured in your `.netrc` file).
3. Click on "Select File" and choose the file you want to upload.
4. Click "Upload". The tool will display an "Uploading..." message.
5. Once the upload is complete, the tool will display the direct HTTP URL to access the uploaded file. You can copy this URL to the clipboard with the "Copy to Clipboard" button.

## .netrc Configuration

To use this tool, you need to have a `.netrc` file in your home directory with the credentials of the FTP server(s). Here's a sample configuration:

```
machine servername login your_username password your_password
```

Replace `servername`, `your_username`, and `your_password` with the appropriate values for your FTP server.

## Problems

- **TLS Dependency**: The tool currently only works with FTP servers that use TLS. Non-TLS servers are not supported.
- **Hardcoded URL Prefix**: The URL prefix is hardcoded, which may not be suitable for all users.
- **No Credential Saving**: The tool does not offer functionality to save new credentials to the `.netrc` file.
- **Windows .netrc Demand**: On Windows, the requirement for a `.netrc` file might seem unconventional.
- **UI Freezing**: The UI freezes during the upload process due to the lack of threading.
- **No Progress Bar**: There's no progress bar during the upload. This is because the `ftp` client from `tcllib` doesn't report progress like the `http` client does.

## Note

This tool is intentionally written for Tcl/Tk 8.5 in order to run natively on OS X without requiring additional installations or configurations.

## Conclusion

The FTP File Uploader tool is designed to streamline the process of uploading files to an FTP server and obtaining a direct HTTP URL. It's a time-saver for those who frequently work with FTP uploads and need quick access to their uploaded files. However, it does come with certain limitations as mentioned in the problems section.

