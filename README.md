# Detailed Technical Description of Keylogger-based Spyware Code

## Dependencies:
- The script utilizes various Python libraries/modules for different functionalities:
  - `email.mime`: For constructing email messages with attachments.
  - `smptlib`: For sending emails via SMTP (Simple Mail Transfer Protocol).
  - `socket`: For retrieving hostname and IP address information.
  - `platform`: For obtaining system-related information like processor details and operating system.
  - `win32clipboard`: For accessing clipboard data in Windows systems.
  - `pynput.keyboard`: For monitoring and logging keyboard input.
  - `time`: For time-related operations and delays.
  - `os`: For interacting with the operating system, including file operations and removal.
  - `scipy.io.wavfile`: For writing audio data to a WAV file.
  - `sounddevice`: For recording audio from the microphone.
  - `cryptography.fernet`: For file encryption using the Fernet symmetric encryption algorithm.
  - `requests.get`: For retrieving the public IP address using an API.
  - `multiprocessing.Process`: For parallel execution of tasks.
  - `PIL.ImageGrab`: For capturing screenshots.

## Configuration:
- Various configuration parameters are set at the beginning of the script:
  - `email_address`: Sender's email address.
  - `password`: Sender's email password.
  - `toaddr`: Recipient's email address.
  - `microphone_time`: Duration (in seconds) for microphone audio recording.
  - `time_iteration`: Duration (in seconds) for each iteration of the keylogger loop.
  - `number_of_iterations_end`: Number of iterations for running the keylogger loop.
  - `file_path`: Directory path for storing captured data.
  - `extend`: Separator used for file path extension.
  - `file_merge`: Merged file path.

## Functions:
- **`send_email(filename, attachment, toaddr)`**: Sends an email with an attachment.
- **`computer_information()`**: Gathers system information like hostname, IP addresses, processor details, etc., and writes it to a file.
- **`copy_clipboard()`**: Copies data from the clipboard and writes it to a file.
- **`microphone()`**: Records audio from the microphone and saves it as a WAV file.
- **`screenshot()`**: Captures a screenshot of the entire screen and saves it as an image file.
- **`run_keylogger()`**: Monitors keyboard input using the `pynput.keyboard` module, logs the keystrokes to a file, and performs actions like taking screenshots and copying clipboard data.
- **`encrypt_files()`**: Encrypts specific files (system information, clipboard data, key logs) using the Fernet encryption algorithm and sends them via email.

## Main Execution:
- The script's main execution flow involves:
  1. Sending an initial email with the keylogger file attached.
  2. Gathering system information and clipboard data.
  3. Recording microphone audio.
  4. Running the keylogger loop, capturing keystrokes, taking screenshots, and copying clipboard data.
  5. Encrypting captured files and sending them via email.
  6. Cleaning up tracked files by deleting them.

## Disclaimer:
- The script includes a disclaimer stating that it is for educational purposes only and warns against unauthorized use due to potential privacy and security law violations.
