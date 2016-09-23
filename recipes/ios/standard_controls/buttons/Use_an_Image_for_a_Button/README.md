---
id:{F3FAE55E-2FF9-37BB-280C-37987E83D1D4}  
title:Use an Image for a Button  
brief:This recipe shows you how to create an image button.  
samplecode:[Browse on GitHub](https://github.com/xamarin/recipes/tree/master/ios/standard_controls/buttons/Use_an_Image_for_a_Button)  
article:[Set Button Text](/recipes/ios/standard_controls/buttons/set_button_text)  
sdk:[UIButton Class Reference](http://developer.apple.com/library/ios/#DOCUMENTATION/UIKit/Reference/UIButton_Class/UIButton/UIButton.html)  
---

<a name="Recipe" class="injected"></a>


# Recipe

Buttons have a number of different states, and you can set the button image
once for all states or assign different values for each state.

To set the ‘default’ image for a button, call `SetImage` for
`UIControlState.Normal` and that image will be used for all states:

```
buttonRect = UIButton.FromType(UIButtonType.RoundedRect);
buttonRect.SetImage(UIImage.FromFile ("star-gold45.png"), UIControlState.Normal);
```

Alternatively you can make each state different, as this image shows:

 ![](Images/ImageButtons.png)

For the `RoundedRect` button type, only two states need to be set (the blue
highlighted color is automatically applied to the transparent parts of the
image):

```
buttonStarRect= UIButton.FromType(UIButtonType.RoundedRect);
buttonStarRect.SetImage (UIImage.FromFile ("star-gold45.png"), UIControlState.Normal);
buttonStarRect.SetImage (UIImage.FromFile ("star-grey45.png"), UIControlState.Disabled);
```

For the `Custom` button type you must supply a separate image for the
`Highlighted` state if you wish the button to look different when pressed.

```
buttonStarCustom = UIButton.FromType(UIButtonType.Custom);
buttonStarCustom.SetImage (UIImage.FromFile ("star-gold45.png"), UIControlState.Normal);
buttonStarCustom.SetImage (UIImage.FromFile ("star-gold45_sel.png"), UIControlState.Highlighted);
buttonStarCustom.SetImage (UIImage.FromFile ("star-grey45.png"), UIControlState.Disabled);
```

 <a name="Additional_Information" class="injected"></a>


# Additional Information

You can also set the different states using Interface Builder by choosing
each one from the drop-down-list in the Attribute Inspector (see the Set Button
Text recipe for an example using Interface Builder).