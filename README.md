# Description
**imgCheckbox** is a jQuery plugin that makes img tags checkable much like Google's recaptcha image selection tool.

## Usage

You can call `imgCheckbox` without any parameters on any jQuery collection containing `<img>` elements.

```JavaScript
$("img.checkable").imgCheckbox();
```

You can have mulitple sets of imgCheckboxes with different parameters

```JavaScript
$("img.checkableGroup1").imgCheckbox();
$("img.checkableGroup2").imgCheckbox({ "graySelected": false });
```

## Options

<table>
    <thead>
        <tr>
            <th>Option</th>
            <th>Type</th>
            <th>Values</th>
            <th>Default</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>checkMarkImage</td>
            <td>URL</td>
            <td>Supports anything your browser support in the <code>background-image</code> property (of a pseudo selector).</td>
            <td>SVG Data URI which draws a white tick on semi transparent green.</td>
        </tr>
        <tr>
            <td>graySelected</td>
            <td>Boolean</td>
            <td>Convenience option: Adds the necessary CSS rules to apply a grayscale filter on selected images.</td>
            <td>true</td>
        </tr>
        <tr>
            <td>scaleSelected</td>
            <td>Boolean</td>
            <td>Convenience option: Adds the necessary CSS rules to apply a downscaling filter on selected images.</td>
            <td>true</td>
        </tr>
        <tr>
            <td>fixedImageSize</td>
            <td>Boolean / String</td>
            <td>Sets a fixed image size to all images (useful if images vary in size). Values can be "200px" or "120px 200px" (not percentages).</td>
            <td>false</td>
        </tr>
        <tr>
            <td>checkMarkSize</td>
            <td>Boolean / String</td>
            <td>Sets a custom size for the image (Useful if your images are very large or very small and the default is not suitable). Values can be "30px" and "20px 30px" (note: percentages do not work).</td>
            <td>"30px"</td>
        </tr>
        <tr>
            <td>scaleCheckMark</td>
            <td>Boolean</td>
            <td>Convenience option: Adds the necessary CSS rules to apply a zooming effect on the checkmark as it appears and disappears.</td>
            <td>true</td>
        </tr>
        <tr>
            <td>fadeCheckMark</td>
            <td>Boolean</td>
            <td>Convenience option: Adds the necessary CSS rules to fade the checkmark in and out.</td>
            <td>false</td>
        </tr>
        <tr>
            <td>addToForm</td>
            <td>Boolean / jQuery</td>
            <td>imgCheckbox can inject the checked elements into the form. If <code>true</code>, imgCheckbox will find a parent form and hook into its submission. A jQuery object can be passed in and the <code>submit</code> listener will attach to it.</td>
            <td>true</td>
        </tr>
        <tr>
            <td>styles</td>
            <td>Object</td>
            <td>For advanced customisation, the full stylesheet is applied using this object.</td>
            <td>(see source)</td>
        </tr>
        <tr>
            <td>preselect</td>
            <td>[Integer]</td>
            <td>To preselect certain elements, use the syntax <code>{ preselect: [0,1,2]}</code></td>
            <td>[]</td>
        </tr>
    </tbody>
</table>

## Advanced

You can add any custom styles using the `styles` option. For example, to add a blur filter to selected images:

```JavaScript
$("img").imgCheckbox({
	"styles": {
		"span.imgCheckbox.imgChked img": {
			// This property will overwrite the default grayscaling, we need to add it back in
			"filter": "blur(5px) grayscale(50%)",

			// This is just css: remember compatibility
			"-webkit-filter": "blur(5px) grayscale(50%)",

			// Let's change the amount of scaling from the default of "0.8"
			"transform": "scale(0.9)"
		}
	}
});
```

## Compatibility

- Firefox
- Chrome
- Opera
- IE8+ (untested on prior versions)
