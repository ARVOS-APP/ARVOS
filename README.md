# ARVOS
ARVOS - AR Viewer Open Source - An open source augmented reality viewer - http://www.arvos-app.com

System Description

ARVOS is a geolocative augmented reality (AR) platform initiated as an open source system. This System Description describes the platform and which components have yet to be implemented. Core functionality for the client has been implemented for 2d augments. Server functionality must be still developed, and core client functionality extended (for instance for 3d objects).

 
Human Actors

    User – the end user who will be viewing the AR content (no background necessary)
    Author – the person who creates the AR content (basic media creation skills)

 
ARVOS System Components

    Client app (implement in both Android and iOS mobile devices).
    Directory Server (manages list of available augments and their properties, such as GPS location, size, scale etc.).
    Augment Server (stores all augments and their media).
    Augment Administration Interface (registers augments and their media stored on Augment Server with augment definitions and properties defined on Directory Server).

 
Requirements on the ARVOS System Components

    Client retrieves list of augments available at current GPS location from directory server.
    Client shows list of available augments to user.
    Client retrieves augment selected by user from Augment Server.
    Client shows retrieved augment to user as geopositioned 2d or 3d overlay on back camera (AR camera). The augment is NOT locked to the display coordinates.
    URL to specific augment launches client, retrieves augment from Augment Server and shows it to user.
    Author uses Administration Interface to upload media for augments to Augment Server.
    Author uses Administration Interface to register augments with Directory Server.

 
Client retrieves list of available augments from directory server (implemented)

    Location information from the device used to determine which augments to list (implemented).
    Retrieval done via http (implemented).
    Content encoded as JSON (implemented).

Client shows list of available augments to user (implemented)

    Title (implemented).
    Author (implemented).
    Thumbnail (implemented).

 
Client retrieves augment selected by user from Augment Server (implemented)

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

Author uses Administration Interface to upload augments to Augment Server (not implemented)

    Web service with html interface
    Author registration, login and authentication required.
    Upload, view and delete media files for augments.
    Store media files for augments on web service
    Augment Server provides augment selected by user to client.

 
Author uses Administration Interface to register augments with Directory Server (not implemented)

    Web service with html interface
    Author registration, login and authentication required.
    Upload, view and delete attributes of augments.
    Store attributes of augments on web service
    Directory server provides list of available augments to client.


