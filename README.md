# Anti CyberBullying


This repository contains source code of our project for Quantum Hack. Anti-CyberBullying is Machine Learning Based Solution to detect offensive and abusive texts from a blog post.


# Description

Our solution is based on microservices architecture and the AI Model can be independently used in any other platform with ease. We've also included a simple blog to show how the API works and how you can use our AI Model an web app together.
Whenever you submit your texts or sentences to our AI Model, it'll detect and tell you if it's offensive or not.

## Technical Aspect

<img src="https://d1.awsstatic.com/logos/aws-logo-lockups/poweredbyaws/PB_AWS_logo_RGB.61d334f1a1a427ea597afa54be359ca5a5aaad5f.png" width=100>  <img src="https://www.devteam.space/wp-content/uploads/2017/03/dockericon-min.png" width=100> <img src="https://static.djangoproject.com/img/logos/django-logo-negative.png" width=100>

### Endpoint of AI Model ( Remote )
```
http://offensivedetectormodel-env.eba-saifiyvj.us-east-1.elasticbeanstalk.com/predict/<string>
```

### Response

```json
{
  "isOffensive":true,
  "status":"success",
  "value":"0.8849344"
}
```

**status** : If any error occured in backend it will say error else it will be set to success. <br>
**isOffensive** : boolean value which says if the text is offensive ( default threshold is 75% ) <br>
**value** : Confidence measure of the AI Model.

# Installation of django project.

```bash
git clone https://github.com/Prasun-Shiwakoti/Anti-CyberBullying.git
cd Anti-CyberBullying/Django\ Webapp
pip install django scipy requests
python manage.py runserver
```

After running these commands, the blog will be hosted and you will be ready to test the endpoint.

# Installation of AI Model

```bash
cd Anti-CyberBullying/AI\ Model
pip install flask tensorflow 
python Deployed_Flask_App.py
```
After running these commands, the AI Model will be hosted on your machine. And you can go to /predict/<string> to test your endpoint.

Feel free to contribute !
