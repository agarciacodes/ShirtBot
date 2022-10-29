# ShirtBot
The Github repository for SZA Shirt Bot Tutorial on TikTok

Welcome to the README page for the SZA Shirt Bot Tutorial! Below is the code necessary to complete this project.


Input the following Python code into Code Source in AWS Lambda:

import tweepy

def handler(event, context):
  # Auth to Twitter
  auth = tweepy.OAuthHandler('API_KEY', 'API_SECRECT_KEY')
  auth.set_access_token('ACCESS_TOKEN', 'ACCESS_TOKEN_SECRET')
  # Create API Object
  api = tweepy.API(auth)
  # Create Tweet
  api.update_status("The audience needs a 'Shirt' remix with @SZA and @DonToliver #STREAMSHIRT #SHIRT")
  
  
Input the following JSON code for the IAM policy:

{
    "Version": "2012-10-17"
    "Statement": [
      {   
          "Sid": "VisualEditor0",
          "Effect": "Allow",
          "Action": "lambda:PublishLayerVersion",
          "Resource": "*"
       }
     ]
}


Input the following command into the Cloud9 Layer command line. Press [ENTER] after each command:

sudo amazon-linux-extras install python3.8
curl -0 https://bootstrap.pypa.io/get-pip.py
python3.8 get-pip.py
mkdir python
python3.8 -m pip install tweepy -t python
zip -r layer.zip
aws lambda publish-layer-version --layer-name lambda-layer --zip file fileb://layer-name.zip --compatible runtimes python3.8 --region us-east-1


  
