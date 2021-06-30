---
title: ARt - Augmented Reality and Art
author: Victor Crespo
date: 
layout: post
permalink: "/portfolio/masters-s2-portolio/augmented-reality-art"
---
Sometimes the story of an artwork in a gallery misses some aspects of the artwork itself. Content and museum curators are in charge of managing and arranging artworks in a gallery or a museum

As a person that likes going to museums and galleries, sometimes it is hard to know detailed information of a specific artwork that is displayed. Generally, every artwork has an attached card with information such as its title, artist, year, and, in some cases, an extended explanation of key details of the artwork such as cultural and social context, techniques, life of the artist, etc. For a person that goes to museums, offering additional information of the artworks can make a difference in their experience. On the other hand, curators may encounter difficulties to show additional information such as lack of space, a medium that is not helpful to show information (in performative art, for example, it might entirely change the performance if the medium is not adequate), lack of information, among others. Showing additional information also presents a challenge in terms of engaging the spectator; if it is only text, spectators might feel overwhelmed by having to read everything.

But, what if we could use a very simple augmented reality (AR) application to show additional information to spectators?

The goal is to create an iPad or iPhone App that a person can take to the NGA and use it to improve their experience by having access to additional information about an artwork.

## Using AR to tell more about an artwork
With this exercise, I tried to create a tool that uses AR to display additional information of selected artworks present in the National Gallery of Australia (NGA).

The selected artworks are:

|[Les amants][amants] [The lovers] by Reneé Magritte|<img src='/assets/img/amants.jpeg' class='w-50'>|
|[La mort d’un esprit][esprit] [Death of a spirit] by Giorgio De Chirico|<img src='/assets/img/death_spirit.jpeg' class='w-50'>|
|[Stroyuschiysya dom][Stroyuschiysya] [House under construction] by Kasimir Malevich|<img src='/assets/img/Stroyuschiysya.jpeg' class='w-50'>|
|[Ngayuku ngura - My Country][ngayuku], 2012 by Barbara Moore|<img src='/assets/img/ngayuku.jpeg' class='w-50'>|
|“Laura” Guess Who card by Hasbro to make tests|<img src='/assets/img/Laura.jpg' class='w-50'>|

Details of why I chose these artworks are explained in following sections

## An introduction to AR
For my first experience working with AR I decided to use Unity and Vuforia to create AR tags and then show an image with additional information on top of them. REasons of why these tools were chosen are:
- Ability to create AR tags with little code
- Ability to create personalized AR track objects
- Databases of assets are managed online and can be personalized
- Both products offer free or student licenses to develop
- Unity/Vuforia is used to develop native iOS Apps and it can export a XCode project to compile

## What makes an image a good AR target
AR tools map features of an image or track object based on different levels of colors and contrast of an image. Vuforia also offers the possibility of tracking standard 3D objects (cubes and cylinders) as well as custom or unusual 3D objects (A 3D model is uploaded to vuforia and processed to get a Unity AR tracking object). Features that Vuforia automatically recognised in the artworks include:

<img src='/assets/img/feature_image_amants.png' class='w-25'>
Identified features in Les Amants

<img src='/assets/img/feature_image_malevich.png' class='w-25'>
Identified features in Stroyuschiysya dom

<img src='/assets/img/feature_image_country.png' class='w-25'>
Identified features in Ngayuku ngura

I chose these artworks because I wanted to have a variety of features in the images, including people, geometric objects, and abstract shapes. These artworks, however, are not a representative sample of all the artworks in the NGA, and further addition to the App should be made if one would like to have more art movements, geographies, and styles.

Vuforia automatically rates the images with a 5 star system trying to address which one is a better AR tag. This rating is aligned with the number of features that Vuforia is able to extract from them.

<img src='/assets/img/ratings.png' class='w-75'>

## Information displayed
The information displayed in the superposed images comes from the NGA website for each of the artworks and includes a more detailed description of the artwork. I created those images using Adobe Photoshop.

<img src='/assets/img/malevich_info.png' class='w-75 bg-dark'>   
Example image of additional information for Stroyuschiysya dom

## Developing the App
Unity’s environment is simple to use but it can have its challenges. In [Unity Learn][ulearn] there are several tutorials that can help to learn the basics of this modeling environment. Learning Unity, however, is beyond the scope of this exercise and rather, I focused on using Unity in combination with Vuforia to create the app.

[Vuforia][vuforia] is an engine used to create AR apps. With this engine, one can easily add tracking objects, mapping features, and advanced computer vision functionalities to virtually any app. It can also recognise real-world shapes and objects, and interact with them in real-world spaces.

<img src='/assets/img/malevich_unity.png' class='w-75'>  
Adding a tracking object to Stroyuschiysya dom in Unity

For each of the images, I created a tracking object, then attached a Material with the image that I previously created, and finally tested it in my computer using the webcam.

<img src='/assets/img/testing_laura.png' class='w-75'>  
Testing the AR tag on a 'Guess Who' card

After successfully tracking the objects, the next step was to create an iPhone or iPad app that can be uploaded to my iPad or iPhone and take it to the museum. Unity does this natively and all I had to do was export the project and then open it with XCode.

## Creating an iOS App

<img src='/assets/img/xcode.png' class='w-75'>  
AR App Xcode Project

XCode lets a developer test their own apps in registered devices. All I had to do was plug my iPhone, configure it to be used as a test device and compile the project. Or at least that is what I would have done if I had an iOS version compatible with the version of XCode I had in my computer. My iPhone updated the night before to iOS 14.1, and XCode 12 (The version I had installed) is compatible with iOS up to 14.0, so I was not able to test the app on my iPhone. Upgrading XCode was also not an option because I ran out of free space in my hard drive. Thankfully my iPad was compatible and I was able to test the app on that device.

## Testing it on the wild
To test the app in a real-world scenario, I went to the NGA and had successful results. The App was able to recognize real-world artworks, and displayed the images I created on top of the artworks.

<img src='/assets/img/testing_amants.png' class='w-75'>  
Testing the app in Les Amants

<img src='/assets/img/testing_mort_esprit.png' class='w-75'>  
Testing the app in La mort d'un esprit

<img src='/assets/img/testing_country.png' class='w-75'>  
Testing the app in Ngayuku ngura

<img src='/assets/img/testing_malevich.png' class='w-75'>  
Testing the app in Stroyuschiysya dom


### Comparing real world and virtual world
<img src='/assets/img/comparison.jpg' class='w-75'>  
Comparing the image on the app and the artwork

## AR App in action

<iframe width="640" height="480" src="https://www.youtube.com/embed/eo0-_ebN65U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" ></iframe>   
Video comparing the real and virtual world


## How to improve and next steps
This exercise showed a promising way of looking and, potentially, changing the way people interact with museums and exhibitions. Because of the nature of curatorial and museographic work, one of the ways in which this App can be improved is by working together with curators and museum administrators to carefully curate the text or images to be superposed on top of artworks. This would prevent biases and/or make clear some assumptions related to the artworks.  
Artists can also be included in the design process, and be sure that their work is respected and the experience of spectators is improved with them in the loop.  
AR offers the possibility to not only show images but also include other types of media, including, 3D animations, videos, geolocalization, etc. If the tracking object is a 3D model of, for example, a sculpture, more than one object can be superposed to the artwork. It also could have real and virtual-world interactions with either the model, the sculpture, or even both.  
QR Codes or other types of AR Tags can be placed alongside artworks so people and spectators could have even more information about them, on top of what is placed over artworks in the AR App.  
Vuforia stores all the databases and images in the App, making it very unoptimised. If this app were to be shipped to an AppStore it would take much space in the smartphone. This can be partially solved by using internet services to download only the data.




[amants]: https://searchthecollection.nga.gov.au/object?uniqueId=148052
[esprit]: https://searchthecollection.nga.gov.au/object?uniqueId=162541
[Stroyuschiysya]: https://searchthecollection.nga.gov.au/object?uniqueId=36797
[ngayuku]: https://searchthecollection.nga.gov.au/object?uniqueId=235874
[ulearn]: https://learn.unity.com/tutorials
[vuforia]: https://developer.vuforia.com