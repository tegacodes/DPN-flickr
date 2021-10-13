# Scrape flickr

## Installation

1. Download this repo

2. Check you have python3 installed on your machine 

`python3 -v`

If not, download and install it from here: https://www.python.org/downloads/ 

3. Open the repository with a text editor. [Get an API key from Flickr](https://www.flickr.com/services/api/misc.api_keys.html) and add it to the file called `credentials.json` which has the following text in it (replace the credentials with your own):

```
{"KEY":"YOUR_API_KEY", "SECRET":"YOUR_API_SECRET"}
```

4. Install software requirements for this script by typing this command into the terminal

`pip3 install -r requirements.txt`

5. Then you can run the program to download with flickr. Check it works. I've used my name as there aren't too many results for it. For common search terms you will get 1000s of results and it will take a long time to download, and a lot of space.

`python3 scraper.py --search "Tega Brain"`

## Usage


To scrape for a particular search term:

`python scraper.py --search "SEARCH TERM"`

You can also add a lat/lng coordinates to specify a geographic bounding box:

`python scraper.py --search "SEARCH TERM" --bbox "minimum_longitude minimum_latitude maximum_longitude maximum_latitude"`

To scrape for a particular group:

`python scraper.py --group "GROUP URL"`

Where GROUP URL is something like https://www.flickr.com/groups/scenery/pool/


Large-sized (1024px width) will be downloaded by default. You can download the original images by passing the flag `--original`.

Limit the number of pages of results downloaded by passing `--max-pages N` where `N` is pages of 500 results each.

`python scraper.py --search "cicada" --max-pages 1`