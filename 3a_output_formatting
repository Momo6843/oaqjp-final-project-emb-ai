import requests,json
def emotion_detector(text_to_analyze):
    url='https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/NlpService/EmotionPredict'
    header={"grpc-metadata-mm-model-id": "emotion_aggregated-workflow_lang_en_stock"}
    obj={ "raw_document": { "text": text_to_analyze } }

    response=requests.post(url,json=obj,headers=header)
    response_json=json.loads(response.text)['emotionPredictions'][0]['emotion']
    list1=list(response_json.values())
    index=list1.index(max(list1))
    sent=list(response_json.keys())
    sent=sent[index]
    response_json['dominant_emotion']=sent
    return response_json