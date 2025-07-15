#include <WiFi.h>
#include<HTTPClient.h>
const char* ssid = "Viknesh";
const char* password ="dynamic17";
const char* serverUrl = "http://console.thingzmate.com/api/v1/device-types/ryg/devices/ryg/http-uplink";
String AuthorizationToken = "Bearer c7592587594efbdd8750002fba897fbf";
#define RED_LED 33
#define YELLOW_LED 25
#define GREEN_LED 26

void setup(){
Serial.begin(115200);
pinMode(RED_LED, OUTPUT);
pinMode(YELLOW_LED, OUTPUT);
pinMode(GREEN_LED, OUTPUT);
WiFi.begin(ssid, password);
while(WiFi.status() != WL_CONNECTED){
delay(1000);
Serial.print(".");
}
Serial.println("Connected to WiFi");
}
void loop(){
 updateTrafficLight(RED_LED, 0, 5000);
 updateTrafficLight(YELLOW_LED, 1, 5000);
 updateTrafficlight(GREEN_LED, 2, 50000;
}

void updateTrafficLight(intledPin, int status, int delayaTime)
{
 digitalWrite(RED_LED, LOW);
 digitalWrite(YELLOW_LED, LOW);
 digitalWrite(GREEN_LED, LOW);
 digitalWrite(ledPin, HIGH);
 sendStatus(status);
 delay(delayTime);
}

void sendStatus(int status){
 if(WiFi.status() == WL_CONNECTED){
   HTTPClient http;
   http.begin(serverUrl);
   http.addHeader("Content-Type", "application/json");
   http.addHeader("Authroization", AuthorizationToken); //Authorization token
   String jsonPayload = "{\"traffic_light\":" +String(status) +"}";
   int httpResponseCode = http.POST(jsonPayload);
   if(httpResponseCode>0){
    Serial.print("HTTP Response code: ");
    Serial.println(httpResponseCode);
  }
Else
{
    Serial.print("Error code: ");
    Serial.println(httpResponseCode);
    }
    http.end();
  }
Else
{
    Serial.println("WiFi Disconnected");
    }
}
    

