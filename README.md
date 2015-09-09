#<img src="http://arvos-app.com/images/arvos_logo_rgb-weiss32.png" width=32></img> ARVOS
<B>ARVOS</B> - <B>A</B>ugmented <B>R</B>eality <B>V</B>iewer <B>O</B>pen <B>S</B>ource -  http://www.arvos-app.com/

<B>Components</B>

<UL>>> Client</UL>

ARVOS-Client Android with 2d augments only: https://github.com/ARVOS-APP/ArViewer_Android

ARVOS-Client Android with integration of the gameplay 3d library: https://github.com/ARVOS-APP/ArViewerGameplay

ARVOS-Client iOS with 2d augments only: https://github.com/ARVOS-APP/ArViewer_iOS

<UL>>> Directory Service</UL> 

The ARVOS augments service: https://github.com/Omarasifshaikh/Arvos-server

<B>System Description</B>

ARVOS is a geolocative augmented reality (AR) platform initiated as an open source system. This System Description describes the platform and which components have yet to be implemented. Core functionality for the client has been implemented for 2d objects. Server functionality must be still developed, and core client functionality extended (for instance for 3d objects).

 
Human Actors

    User – the end user who will be viewing the AR content (no background necessary)
    Author – the person who creates the AR content (basic media creation skills)

 
ARVOS System Components

    Client app (implement in both Android and iOS mobile devices).
    Directory Service (manages list of available channels of augments and their properties, such as author, description, GPS location, etc.).
    Augment Service (stores all augments and their media).
    Channel Administration Interface (registers augments and their media stored on Augment Service with channel definitions and properties defined on Directory Service).

 
Requirements on the ARVOS System Components

    - Client retrieves list of channels available at current GPS location from directory service.
    - Client searches for list of channels available at current GPS location from directory service.
    - Client shows list of available channels to user.
    - Client retrieves augment of channel selected by user from Augment Service.
    - Client shows retrieved augment to user as geopositioned 2d or 3d overlay on back camera (AR camera). The augment is NOT locked to the display coordinates.
    - URL to specific channel launches client, retrieves channel's augment from Augment Service and shows it to user.
    - Author uses Administration Interface to upload media for augments to Augment Service.
    - Author uses Administration Interface to register channel with Directory Service.

 
Client retrieves list of channels available at current GPS location from directory service (implemented)

    Location information from the device used to determine which channels to list (implemented).
    Retrieval done via http (implemented).
    Content encoded as JSON (implemented).

Client searches for list of channels available at current GPS location from directory service (implemented)

    Location information from the device used to determine which channels to list.
    Searches can be done by channel name or author name.
    Retrieval done via http (implemented).
    Content encoded as JSON (implemented).
    
Client shows list of available channels to user (implemented)

    Title (implemented).
    Author (implemented).
    Thumbnail (implemented).
 
Client retrieves augment of channel selected by user from Augment Service (implemented)

    Retrieval done via http (implemented).
    Content encoded as JSON (implemented).

 
Client shows retrieved augment to user (partially implemented)

    Use location and orientation information of device to show augment in correct scale, direction and orientation (implemented).
    Text labels have to be rendered (2d label with text)
    2D image augments have to be rendered (jpg, png etc) (implemented).
    3D object augments have to be rendered
        Object format has to be renderable on both Android and iOS
        Ideally with vertex animations (autoplay and/or user triggered)
        Jpg, and png and movie textures (with alpha, movies autoplay and/or user triggered)
    Sound augments should be playable (autoplay and/or user triggered)
    All augments should be clickable (implemented).
        animatable (transform, rotate, scale, swap (implemented).
        should be able to link to other online content (webpages, etc) (implemented).

Author uses Administration Interface to upload augments to Augment Service (not implemented)

    Web service with html interface
    Author registration, login and authentication required.
    Upload, view and delete media files for augments.
    Store media files for augments on web service
    Augment service provides augment selected by user to client.

 
Author uses Administration Interface to register channels with Directory Service (not implemented)

    Web service with html interface
    Author registration, login and authentication required.
    Upload, view and delete attributes of channels.
    Store attributes of channels on web service
    Directory service provides list of available channels to client.


