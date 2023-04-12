# BorderTest

This repo contains code to reproduce a possible .NET MAUI bug with the Border control.

Steps to reproduce:

Load BorderTest.sln and run the .NET MAUI app. On Windows ARM it looks like this -- the Border in the bottom cell expands past the bottom of the page:

![image](https://user-images.githubusercontent.com/7516297/231586270-dbe54377-2c37-4731-8827-500b2a015378.png)

Make the window shorter by clicking on the bottom of the window frame and dragging up and the other controls resize with the Grid, but the Border does not:

![image](https://user-images.githubusercontent.com/7516297/231586564-2ac14c67-22bd-4067-8f0f-ebb8cd639aa1.png)

Make the window smaller by clicking the lower right corner and dragging up and left just a few pixels, and the Border control corrects itself and looks like it should:

![image](https://user-images.githubusercontent.com/7516297/231586702-f3c84d91-446e-4257-9e7d-5de1814ceeb5.png)

Note that the Button also resizes itself correctly, so this may be a problem with the Grid and not the Border.


