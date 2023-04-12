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

## Workload list

```
C:\Users\andrewstellman\source\repos\BorderTest>dotnet workload list

Installed Workload Id      Manifest Version       Installation Source
---------------------------------------------------------------------
runtimes-windows           7.0.3/7.0.100          VS 17.6.33417.168
maui-windows               7.0.59/7.0.100         VS 17.6.33417.168
maui-maccatalyst           7.0.59/7.0.100         VS 17.6.33417.168
maccatalyst                16.2.1024/7.0.100      VS 17.6.33417.168
maui-ios                   7.0.59/7.0.100         VS 17.6.33417.168
ios                        16.2.1024/7.0.100      VS 17.6.33417.168
maui-android               7.0.59/7.0.100         VS 17.6.33417.168
android                    33.0.26/7.0.100        VS 17.6.33417.168

Use `dotnet workload search` to find additional workloads to install.
```

## Cannot reproduce on MAUI macOS

When I run on MAUI macOS the page renders as expected:

<img width="962" alt="image" src="https://user-images.githubusercontent.com/7516297/231587193-7e677116-71b1-4838-bb64-3e26a8d02530.png">

```
andrewstellman@Andrews-MBP Projects % dotnet workload list

Installed Workload Id      Manifest Version      Installation Source
--------------------------------------------------------------------
maui-maccatalyst           7.0.81/7.0.100        SDK 7.0.200        
maui-ios                   7.0.81/7.0.100        SDK 7.0.200        
maui-android               7.0.81/7.0.100        SDK 7.0.200        

Use `dotnet workload search` to find additional workloads to install.
```

