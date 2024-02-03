This API will encodes your data into a QR code. You can pass any url or string into the "data" param. The "data" param is the only required field.

Both GET and POST endpoints are available and work exactly the same. Let's look at some examples using GET

## Simple Example:
GET https://simple-qr-code-generator-cheap-and-efficient.p.rapidapi.com/api/v1/?data=https://google.com
This will return a black and white QR code in png image format. Scanning the QR code will take the user to https://google.com

## All available query params:
* **data** (REQUIRED)
	* Any url or string that you want the QR code to output when scanned. No hard limit applies to the length, however there is a soft limit of 10,000px image width/height. The longer your "data" string, the larger the QR code will become. If you are passing a very long string, try reducing the "scale" parameter.
* **response-type** (OPTIONAL) 
	* Specifies whether you want the API to return an image or a [dataurl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URLs)
	* Default value: "image"
	* Allowed values: "image", "dataurl"
* **file-type** (OPTIONAL) 
	* Specifies the image format for the QR code 
	* Default value: "png" 
	* Allowed values: "png", "jpeg", "jpg", "svg", "pdf"
* **scale** (OPTIONAL) 
	* Specifies the relative size of the image. A larger number will give you a larger image. 
	* Default value: "10" 
	* Allowed values: 1-100.
* **color** (OPTIONAL) 
	* Specifies the color of the QR code (the black part of a traditional QR code)
	* Default value: "#FFFFFF" (black)
	* Allowed values: Any valid HTML color.
* **bg-color** (OPTIONAL) 
	* Specifies the background color of the QR code (the white part of a traditional QR code)
	* Default value: "#000000" (white)
	* Allowed values: Any valid HTML color.

## All Param Example:
GET https://simple-qr-code-generator-cheap-and-efficient.p.rapidapi.com/api/v1/?data=https://google.com&response-type=dataurl&file-type=svg&scale=15&color=blue&bg-color=white

This will return a dataurl for a QR code in svg format that is blue and white. Scanning the QR code will take the user to https://google.com

Similarly, you can instead send a POST request to the same URL with the body structured like:
```
{
    "data":"https://google.com",
    "response-type":"dataurl",
    "file-type":"svg",
    "scale":"15",
    "color":"blue",
    "bg-color": "white"
}
```
