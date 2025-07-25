import requests
import time
import copy
ad1 = {
"offerItems" : [439945864],
"requestItems" : [],
"requestTags" : ["downgrade","demand"],
"offer_robux" : 64
}
ad2 = {
"offerItems" : [376809691],
"requestItems" : [],
"requestTags" : ["downgrade","demand"],
"offer_robux" : 64
}
ad3 = {
"offerItems" : [440739240],
"requestItems" : [],
"requestTags" : ["downgrade","demand"],
"offer_robux" : 64
}
ad4 = {
"offerItems" : [568920079],
"requestItems" : [],
"requestTags" : ["downgrade","demand"],
"offer_robux" : 64
}
ad5 = {
"offerItems" : [4390890198],
"requestItems" : [494291269],
"requestTags" : [],
"offer_robux" : 64
}
ad6 = {
"offerItems" : [73829193],
"requestItems" : [494291269],
"requestTags" : [],
"offer_robux" : 64
}

ads = [ad1,ad3,ad4,ad5]
roliVeri = ""
cookies = {"_RoliVerification":roliVeri}
constWaitTime = 60*30
failWaitTime = 60


def post(ad):
    try:
        data = {"player_id":491246505,"offer_item_ids":ad["offerItems"],"request_item_ids":ad["requestItems"],"request_tags":ad["requestTags"],"offer_robux":ad["offer_robux"]}
        response = requests.post("https://api.rolimons.com/tradeads/v1/createad",json=data,cookies=cookies,timeout = 8)
    except Exception as e:
        print("error "+e)
        return
    
    success = response.json()["success"]
    if success == False:
        print(response.json()["message"])
        if response.json()["code"] == 7104:
            ads.remove(ad)
        return False
    else:
        print(response.json(),ads)
        return True

while True:
    copy_ads = copy.deepcopy(ads)
    for ad in copy_ads:
        success = post(ad)
        if success:
            time.sleep(constWaitTime)
        else:
            time.sleep(failWaitTime)
    




    

    
