# fdp


#define BLYNK_TEMPLATE_ID "TMPL37IzK8bfV"
#define BLYNK_TEMPLATE_NAME "FDP"
#define BLYNK_AUTH_TOKEN "MaYJGoenFkED-7SdLrA70NpnaRsaGFMI"
#include <WiFi.h>
#include <BlynkSimpleEsp32.h>

char ssid[] = "fdp";
char pass[] = "admin@123";

#define LED_PIN 2   // Built-in LED

BLYNK_WRITE(V0)
{
  int value = param.asInt();

  if (value == 1)
  {
    digitalWrite(LED_PIN, HIGH);
  }
  else
  {
    digitalWrite(LED_PIN, LOW);
  }
}

void setup()
{
  pinMode(LED_PIN, OUTPUT);

  Serial.begin(115200);

  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);
}

void loop()
{
  Blynk.run();
}
