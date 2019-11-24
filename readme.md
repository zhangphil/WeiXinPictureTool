# WeiXinPictureTool
## Usage
1. Import this project as a module
2. Write these code to open IMGEditActivity (no need to parse `content://` uri first)

```java
Intent intent = new Intent(MainActivity.this, IMGEditActivity.class);
intent.putExtra(IMGEditActivity.INT_IMAGE_URI, uri);
intent.putExtra(IMGEditActivity.INT_IMAGE_SAVE_URI, "edited.png");
startActivityForResult(intent, 1);

@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
    if (requestCode == 1) {
        Uri editedUri = data.getData();
        // ...
    }
}
```