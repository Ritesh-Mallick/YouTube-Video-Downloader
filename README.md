# YouTube-Video-Downloader
- This Project performs several tasks related to YouTube videos, such as extracting information about the video and providing an option to download it by using Python libraries like pytube and yt-dlp. 
## Step-by-Step Breakdown
### 1. Installing Required Packages:
-  Install and upgrade the pytube library. This library allows you to interact with YouTube videos.
   ```
   pip install pytube3
   pip install --upgrade pytube
   ```
-  Install yt-dlp, a popular YouTube downloader with more advanced features.
    ```
    pip install yt-dlp
    ```
### 2. Importing the Libraries:
- Import the YouTube class from the pytube library, which is used to interact with YouTube videos.
- Import the YoutubeDL class from yt-dlp, used for downloading videos.
    ```
    from pytube import YouTube
    from yt_dlp import YoutubeDL
    ```
### 3.	Getting the YouTube Video Link:
- Prompt the user to enter the YouTube video URL.
    ```
    link = input("Enter youtube video")
    ```
### 4. Extracting Video Information:
-  Create a YouTube object for the provided video link.
-  We can perform different operations like getting video title, description, total views count etc. by using different attributes of Youtube object.
    ```
    	yt = YouTube(link)
      print("Title :", yt.title)
      print("Duration :", yt.length)
      print("Description :", yt.description)
      print("Ratings :", yt.rating)
    ```
### 5.	Downloading the Video:
- Downloads the video if user chooses yes with the best best quality available.
    ```
    download_option = input("Do you want to download this video? (yes/no): ").lower()
    if download_option == "yes":
        ydl_opts = {'format': 'best'}
        with YoutubeDL(ydl_opts) as ydl:
            print("Downloading...")
            ydl.download([yt])
            print("Download completed.")
    else:
        print("Download aborted.")
    ```
