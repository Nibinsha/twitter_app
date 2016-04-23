from django.shortcuts import render
import requests
from requests_oauthlib import OAuth1
from django.shortcuts import render_to_response
import json

def twitterapp(request):
    return render(request, 'blog/twitterapp.html',{})



def tweets(request):
    if request.method == 'POST':
       twitter_id = request.POST.get('screen_name','')
       num = request.POST.get('count','')
     
       auth = OAuth1('TxHMFbTrXLoxGwdNi9EENKFzN','OX8dvppxFGiviPZEzecpPKkpkm8j0hnWhwtWETuNEGB4fk2AEc','1889500886-qIkta3TT3tLt16AI4u0j6rqi9dXCUhR9QFZlylm','CrAJxzP1NU9lKbQOv8ijAHFO8eWd7FljtblNmnTxxQlGX')
       lis = [] 
       r = requests.get('https://api.twitter.com/1.1/statuses/user_timeline.json?screen_name='+twitter_id+'&count='+num,auth=auth)
       tw = ""
       us = r.json()
       num = int(num)
       for i in range(num):
          
           lis.append(us[i]["text"])
       return render(request, 'blog/tweets.html', {'tweets':lis})




# Create your views here.
