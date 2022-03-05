# Imgflip API Notes

The full documentation of the [Imgflip API](https://imgflip.com/api) is very light.  Below are a series of Thunderclient requests to show different possible use cases for our needs.

Some things to note about the API data:

* There is only one `GET` route that fetches the top 100 memes from the last 30 days.
  * We can cache the whole data object once and reference the cache for all local operations.

## GET 

### Request

`https://api.imgflip.com/get_memes`

### Response

```json
{
  "success": true,
  "data": {
    "memes": [
      {
        "id": "181913649",
        "name": "Drake Hotline Bling",
        "url": "https://i.imgflip.com/30b1gx.jpg",
        "width": 1200,
        "height": 1200,
        "box_count": 2
      },
      {
        "id": "87743020",
        "name": "Two Buttons",
        "url": "https://i.imgflip.com/1g8my4.jpg",
        "width": 600,
        "height": 908,
        "box_count": 3
      },
      // ...and 98 more just like this
    ]
  }
}
```

## POST 

### Request

To caption an image, we submit a `POST` request to `https://api.imgflip.com/caption_image` with the following request body:

NOTE: 

 * Username and Password are an account I made specifically for this. Feel free to use it, as there's nothing sensitive about it at all. Please don't change any of the settings.
 * Boxes will need to be made based on the `box_count` property of the meme being edited.

```json
{
  "template_id": "93895088",
  "username": "Deprecated-Dependencies",
  "password": "Vile Deep Lucky",
  "text0": "",
  "text1": "",
  "font": "arial",
  "max_font_size": "50",
  "boxes": [
    {
      "text": "Box 1 Text",
      "color": "#ffffff",
      "outline_color": "#000000"
    },
        {
        "text": "Box 2 Text",
        "color": "#ffffff",
        "outline_color": "#000000"
    },
        {
        "text": "Box 3 Text",
        "color": "#ffffff",
        "outline_color": "#000000"
    },
        {
        "text": "Box 4 Text",
        "color": "#ffffff",
        "outline_color": "#000000"
    }
  ]
}
```

HOWEVER we cannot send the request as a JSON object.  We have to send the request with the request header `Content-type: application/x-www-form-urlencoded` and the request parameters in the body of the request.  Imgflip will not send a successful response if the parameters are in the URL.

### Response

Success:

```json
{
  "success": true,
  "data": {
    "url": "https://i.imgflip.com/67k84i.jpg",
    "page_url": "https://imgflip.com/i/67k84i"
  }
}
```

Failure: 

```json
{
    "success": false,
    "error_message": "Some hopefully-useful statement about why it failed"
}
```


