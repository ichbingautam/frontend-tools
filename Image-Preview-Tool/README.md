image-preview-before-upload-using-javaScript
Viewing an image before is one of the best feature that every website must provide to their user. It allows user to check whether they are going to upload the correct image or not, or if the image looks good or not.

 

In this tutorial we are going to build this functionality of viewing image before upload using JavaScript and JQuery.

 

HTML Code
 

<div class="wrap">
<div class="header">Image Preview Before Upload using JavaScript </div>
<form method="post" action="">
<label for="upload">Upload Image: </label>
<input type="file" name="upload" id="upload" onchange="previewImage(this);">
</form>


<div id="preview">
<h3>Image Preview</h3>
<img src="http://via.placeholder.com/380x200" id="preview-image">
</div>


</div>

 
CSS Code
 

.wrap{
  width:400px;
  margin-left:auto;
  margin-right:auto;
  font-family: sans-serif;
  box-shadow:1px 1px 5px #ccc;
}
.header{
  background: #f2f2f2;
  margin:0px 0px 0px 0px;
  padding:20px;
  border-bottom:1px solid #f2f2f2;
  font-weight:normal;
}
form{
  padding:10px 10px 0px 10px;
}
input[type="file"]{
  padding: 5px 10px;
  border:1px solid #ccc;
  margin: 5px 5px 5px 0px;	
}
input[type="submit"]{
  background: #333;
  color: #fff;
  padding: 10px 5px;
  border:1px solid #333;
  cursor:pointer;
}
h3{
  font-weight:normal;
}
#preview{
  padding:0px 10px 10px 10px;
}
#preview-image{
  background: #333;
  min-height:200px;
  width: 100%;
}
 
JavaScript Code
NOTE: Include jquery file.
The core part of this program is in JavaScript. The previewImage function takes the input image. The FileReader object lets web applications asynchronously read the contents of files.

 


<script src="jquery-1.9.1.js"></script>
<script>
function previewImage(input) {
  if (input.files && input.files[0]) {
    var reader = new FileReader();
    reader.onload = function (e) {
      $('#preview-image').attr('src', e.target.result);
    }
    reader.readAsDataURL(input.files[0]);
  }
}
</script>
