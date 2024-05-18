# # Video-On-Demand
Storage for video projects
## 0. VOD Project Overview
1. Home page
* Show the video to the user, and you can view the video you want according to the user's click.
2. Login screen
* When you press the login / membership button, you will be directed to the login page, and you can log in to the backend server via Oauth.
3. jwt token
* When the Oauth login is completed, the jwt token is stored in the front local storage, and the authentication method has been strengthened so that it does not burden memory like the method of the existing session.
4. AWS and Storage
* We are going to rent a server from Amazon services for video streaming.
5. Community building
* A community ecosystem was established to revitalize the community among users.

|Repository|Description|URL|
|:---|:---|:---|
|awm-v2-proxy|Protects the gateway from external access.|[link](https://github.com/ahr-i/awm-v2-proxy)|
|awm-v2-gateway|Serves as the initial point of contact for clients.|[link](https://github.com/ahr-i/awm-v2-gateway)|
|awm-v2-authentication-server|Handles client authentication and issues or validates JWT tokens.|[link](https://github.com/ahr-i/awm-v2-authentication-server)|
|awm-v2-location-manager|Provides functions for querying, registering, and modifying information about places.|[link](https://github.com/ahr-i/awm-v2-location-manager)|
|awm-v2-image-processing-server|We offer image processing services, including image-based location search.|[link](https://github.com/ahr-i/awm-v2-image-processing-server)|
|awm-v2-community-server|Offers a community where users can write, view, and modify posts.|[link](https://github.com/ahr-i/awm-v2-community-server)|
