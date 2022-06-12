Extract your Spotify streaming history, connect to the Spotify API to acquire the songs' features, and organize everything into a handy .csv file. 

Medium article: https://towardsdatascience.com/get-your-spotify-streaming-history-with-python-d5a208bbcbd3

Dependencies:

<ul>
<li>Pandas: https://pandas.pydata.org/</li>
<li>Spotipy: https://spotipy.readthedocs.io/</li>
<li>Requests: https://requests.readthedocs.io/en/master/</li>
</ul>

Instructions:

## Virtual Environment Setup
  
  Setup a venv environment, clone repo and prepare to fill in config.py with the information from following steps

  ### macOS/Linux - You may need to run sudo apt-get install python3-venv first
  python3 -m venv .venv-ChooseName

  ### Open the venv
  git clone https://github.com/Username/Repositoryname.git

  ### Install requirements
  pip install -r requirements.txt

## Getting the App to run

1. Enter your account dashboard at https://www.spotify.com/. In the privacy settings, apply for the download of your personal data. This might take a few days. When you get the mail, download the zip archive and place the MyData folder into the script folder. 

2. Sign up at Spotify for Developers at https://developer.spotify.com/. Select 'Create an app'. From the app panel, take note of your Client ID and Client Secret. Then select 'Edit settings' and whitelist a link in Redirect URIs. If you don't have a site, http://localhost:portnumber/callback will do. Take note of this link too.

Note! Keep these values as safe or safer as your Spotify login information

3. Open config.py and insert your Spotify username, Client ID, Client Secret and Redirect URI. You can leave the scope as is.

4. Execute main.py. If it's the first time, Spotipy will need user authentication. It will try to open a link in your browser, or failing that, will print the link in your console/terminal. Follow the link, log in with your Spotify account, and accept the permissions. Then you will be taken to the Redirect URI. Paste the URI in the console. 

5. The script will now reconstruct your listening history, connect to Spotify API to get the song IDs, and then use those IDs to extract the features. 

5. If you still miss IDs or features, you can run the script again and retry your luck with the API. Collected IDs and features are saved locally, so we don't make repeated requests. 

6. Find your song history, complete with features, in 'output/final.csv'. Happy exploration! 
