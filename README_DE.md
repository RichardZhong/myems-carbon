# MyEMS

 [中文](./README.md) | [EN](./README_EN.md) | [DE](./README_DE.md)

 [![Documentation Status](https://readthedocs.org/projects/myems/badge/?version=latest)](https://myems.readthedocs.io/en/latest/?badge=latest)
 [![Maintainability](https://api.codeclimate.com/v1/badges/e01a2ca1e833d66040d0/maintainability)](https://codeclimate.com/github/MyEMS/myems/maintainability)
 [![Test Coverage](https://api.codeclimate.com/v1/badges/e01a2ca1e833d66040d0/test_coverage)](https://codeclimate.com/github/MyEMS/myems/test_coverage)
 [![Total alerts](https://img.shields.io/lgtm/alerts/g/MyEMS/myems.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/MyEMS/myems/alerts/)
 [![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/MyEMS/myems.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/MyEMS/myems/context:python)
 [![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/MyEMS/myems.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/MyEMS/myems/context:javascript) 
 [![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/MyEMS/myems/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/MyEMS/myems/?branch=master)
 [![Build Status](https://scrutinizer-ci.com/g/MyEMS/myems/badges/build.png?b=master)](https://scrutinizer-ci.com/g/MyEMS/myems/build-status/master)
 [![Codacy Badge](https://app.codacy.com/project/badge/Grade/b2cd6049727240e2aaeb8fc7b4086166)](https://www.codacy.com/gh/MyEMS/myems/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=MyEMS/myems&amp;utm_campaign=Badge_Grade)

## MyEMS-Einführung

MyEMS ist ein industrie führend Open Source Energiemanagementsystem, das auf Cloud-Computing-, IOT-, Big Data- und AI-Technologien basiert. MyEMS kann für eine standardmäßige und leistungsstarke integrierte Energiemanagement-Serviceplattform verwendet werden.
MyEMS wird von einem erfahrenen Entwicklungsteam entwickelt und gewartet, und der Quellcode des Systems wird unter MIT-Lizenz veröffentlicht.

## MyEMS Architektur

![MyEMS Architecture Function View](/docs/images/architecture-function-view.png)

![MyEMS Architecture Site View](/docs/images/architecture-site-view.png)


## MyEMS Komponenten (GCommunity Edition)

Dieses Projekt besteht aus folgenden Komponenten:

### MyEMS Database (SQL)

[Installieren database](./database/README.md)

### MyEMS API (Python)

[Installieren myems-api](./myems-api/README.md)

### MyEMS Admin UI (AngularJS)

[Installieren admin UI](./admin/README.md)

### MyEMS Modbus TCP Acquisition Service (Python)

[Installieren myems-modbus-tcp](./myems-modbus-tcp/README.md)

### MyEMS Cleaning Service (Python)

[Installieren myems-cleaning](./myems-cleaning/README.md)

### MyEMS Normalization Service (Python)

[Installieren myems-normalization](./myems-normalization/README.md)

### MyEMS Aggregation Service (Python)

[Installieren myems-aggregation](./myems-aggregation/README.md)

### MyEMS Web UI (ReactJS)

[Installieren web UI](./web/README.md)

### Docker Docker-compose Installieren 

```
git clone https://gitee.com/myems/myems.git 
```

Ändern Sie die Datenbankkonfiguration in den folgenden Dateien
Angenommen, die Datenbank-IP lautet 192.168.2.2
```
sudo nano myems-api/config.py 
sudo nano myems-aggregation/config.py 
sudo nano myems-cleaning/config.py 
sudo nano myems-modbus-tcp/config.py 
sudo nano myems-normalization/config.py 

# host: '127.0.0.1' => 'host': '192.168.2.2'
```

Ändern Sie den location '/api' von nginx.conf in web und admin
Angenommen, die Host-IP lautet 192.168.2.3
```
sudo nano admin/nginx.conf
sudo nano web/nginx.conf
# proxy_pass http://127.0.0.1:8000/;  => proxy_pass http://192.168.2.3:8000/; 
```

Verpacken Sie das web, um Produktdateien zu generieren
```
cd myems/web
npm install
npm run build
```
Mit docker-compose installieren
```
cd myems
docker-compose up -d 
```

## Editionen vergleichen

| Eigenschaften                    | Gemeinschaftsausgabe | Enterprise Edition | Erläuterung   |
| :---                             |      :----:          |  :----:            |  :----:       |
| Open Source                      | ✔️              | ❌      |                      |
| Pricing                          | Free            | Pay for Projects |              |
| Change Name and Logo             | ️❌             | ✔️        |                      |
| Modbus TCP                       | ✔️             | ✔️        |                      |
| Data Points Number               | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Meters Number                    | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Spaces Number                    | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Equipments Number                | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Tenants Number                   | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Stores Number                    | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Shopfloors Number                | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Combined Equipments Number       | Unbegrenzt     | Unbegrenzt | Die tatsächliche Zahl ist durch die obere Grenze der Serverressourcen begrenzt |
| Docker                           | ✔️             | ✔️        | https://www.docker.com/ |
| Kubernetes                       | ❌             | ✔️        | https://kubernetes.io/ |
| MySQL                            | ✔️             | ✔️        | http://mysql.com/    |
| MariaDB                          | ✔️             | ✔️        | https://mariadb.org/ |
| SingleStore                      | ❌            | ✔️        | https://www.singlestore.com/ |
| AWS Cloud                        | ✔️             | ✔️        | https://aws.amazon.com/ |
| AZure Cloud                      | ✔️             | ✔️        | https://azure.microsoft.com/ |
| Alibaba Cloud                    | ✔️             | ✔️        | https://aliyun.com/ |
| Private Cloud                    | ✔️             | ✔️        |                      |
| Data Comparison                  | ✔️             | ✔️        | Jahr für Jahr, Monat für Monat, Freier Vergleich, Kein Vergleich |
| Excel Exporter                   | ✔️             | ✔️        | Tabellen, Liniendiagramme, Säulendiagramme, Kreisdiagramme |
| Meter/Energy Data                | ✔️             | ✔️        |                      |
| Meter/Cost Data                  | ✔️             | ✔️        |                      |
| Meter/Trend Data                 | ✔️             | ✔️        |                      |
| Meter/Realtime Data              | ✔️             | ✔️        |                      |
| Meter/Master Meter Submeters Balance | ✔️         | ✔️        |                      |
| Meter/Offline Meter Energy Data  | ✔️             | ✔️        |                      |
| Meter/Offline Meter Cost Data    | ✔️             | ✔️        |                      |
| Meter/Virtual Meter Energy Data  | ✔️             | ✔️        |                      |
| Meter/Virtual Meter Cost Data    | ✔️             | ✔️        |                      |
| Meter/Meter Tracking             | ✔️             | ✔️        |                      |
| Space/Energy Category Data       | ✔️             | ✔️        |                      |
| Space/Energy Item Data           | ✔️             | ✔️        |                      |
| Space/Cost Data                  | ✔️             | ✔️        |                      |
| Space/Output Data                | ✔️             | ✔️        |                      |
| Space/Income Data                | ✔️             | ✔️        |                      |
| Space/Efficiency Data            | ✔️             | ✔️        |                      |
| Space/Load Data                  | ✔️             | ✔️        |                      |
| Space/Statistics                 | ✔️             | ✔️        |                      |
| Space/Saving Data                | ❌             | ✔️        | Erfordert eine Komponente zur Vorhersage des Energieverbrauchs |
| Equipment/Energy Category Data   | ✔️             | ✔️        |                      |
| Equipment/Energy Item Data       | ✔️             | ✔️        |                      |
| Equipment/Cost Data              | ✔️             | ✔️        |                      |
| Equipment/Output Data            | ✔️             | ✔️        |                      |
| Equipment/Income Data            | ✔️             | ✔️        |                      |
| Equipment/Efficiency Data        | ✔️             | ✔️        |                      |
| Equipment/Load Data              | ✔️             | ✔️        |                      |
| Equipment/Statistics             | ✔️             | ✔️        |                      |
| Equipment/Saving Data            | ❌            | ✔️        | Erfordert eine Komponente zur Vorhersage des Energieverbrauchs |
| Equipment/Batch Analysis         | ✔️             | ✔️        |                      |
| Equipment/Equipment Tracking     | ✔️             | ✔️        |                      |
| Tenant/Energy Category Data      | ✔️             | ✔️        |                      |
| Tenant/Energy Item Data          | ✔️             | ✔️        |                      |
| Tenant/Cost Data                 | ✔️             | ✔️        |                      |
| Tenant/Load Data                 | ✔️             | ✔️        |                      |
| Tenant/Statistics                | ✔️             | ✔️        |                      |
| Tenant/Saving Data               | ❌             | ✔️        | Erfordert eine Komponente zur Vorhersage des Energieverbrauchs |
| Tenant/Tenant Bill               | ✔️             | ✔️        |                      |
| Store/Energy Category Data       | ✔️             | ✔️        |                      |
| Store/Energy Item Data           | ✔️             | ✔️        |                      |
| Store/Cost Data                  | ✔️             | ✔️        |                      |
| Store/Load Data                  | ✔️             | ✔️        |                      |
| Store/Statistics                 | ✔️             | ✔️        |                      |
| Store/Saving Data                | ❌             | ✔️        |                      |
| Shopfloor/Energy Category Data   | ✔️             | ✔️        |                      |
| Shopfloor/Energy Item Data       | ✔️             | ✔️        |                      |
| Shopfloor/Cost Data              | ✔️             | ✔️        |                      |
| Shopfloor/Load Data              | ✔️             | ✔️        |                      |
| Shopfloor/Statistics             | ✔️             | ✔️        |                      |
| Shopfloor/Saving Data            | ❌             | ✔️        | Erfordert eine Komponente zur Vorhersage des Energieverbrauchs |
| Combined Equipment/Energy Category Data | ✔️      | ✔️        |                      |
| Combined Equipment/Energy Item Data     | ✔️      | ✔️        |                      |
| Combined Equipment/Cost Data            | ✔️      | ✔️        |                      |
| Combined Equipment/Output Data          | ✔️      | ✔️        |                      |
| Combined Equipment/Income Data          | ✔️      | ✔️        |                      |
| Combined Equipment/Efficiency Data      | ✔️      | ✔️        |                      |
| Combined Equipment/Load Data            | ✔️      | ✔️        |                      |
| Combined Equipment/Statistics           | ✔️      | ✔️        |                      |
| Combined Equipment/Saving Data          | ❌     | ✔️        | Erfordert eine Komponente zur Vorhersage des Energieverbrauchs |
| Combined Equipment/Batch Analysis       | ✔️      | ✔️        |                      |
| Energy Dashboard                 | ✔️             | ✔️        |                      |
| Energy Flow Diagram              | ✔️             | ✔️        |                      |
| Distribution System              | ✔️             | ✔️        |                      |
| REST API                         | ✔️             | ✔️        |                      |
| Web UI                           | ✔️             | ✔️        |                      |
| Admin UI                         | ✔️             | ✔️        |                      |
| BACnet/IP                        | ❌️             | ✔️        | http://www.bacnet.org/ |
| MQTT Subscriber                  | ❌             | ✔️        | https://mqtt.org/ |
| Modbus RTU                       | ❌             | ✔️        | https://modbus.org/ |
| OPC UA                           | ❌             | ✔️        | https://opcfoundation.org/ |
| OPC DA                           | ❌             | ✔️        | https://opcfoundation.org/ |
| Siemens S7                       | ❌             | ✔️        | https://siemens.com/ |
| IEC 104                          | ❌             | ✔️        | IEC 60870-5-104 https://en.wikipedia.org/wiki/IEC_60870-5 |
| Johnson Controls Metasys API     | ❌             | ✔️        | https://www.johnsoncontrols.com/ |
| Honeywell EBI                    | ❌️             | ✔️        | https://www.honeywell.com/ |
| SIEMENS Desigo CC                | ❌             | ✔️        | https://siemens.com/ |
| QWeather API                     | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz |
| FDD Rule Engine                  | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz |
| Advanced Reporting Engine        | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| Prognose des Energieverbrauchs   | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| Graphics Drawing Tool            | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz |
| Equipments Remote Control        | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| BACnet Server                    | ❌             | ✔️        | http://www.bacnet.org/ |
| Modbus TCP Server                | ❌             | ✔️        | https://modbus.org/ |
| OPC UA Server                    | ❌             | ✔️        | https://opcfoundation.org/ |
| MQTT Publisher                   | ❌             | ✔️        | https://mqtt.org/ |
| iOS APP                          | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| Android APP                      | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| WeChat Mini Program              | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| Alipay Mini Program              | ❌             | ✔️        | Erfordert eine Standardkomponentenlizenz oder eine benutzerdefinierte Entwicklung |
| IPC Hardware Gateway (Data Acquisition and Remote Control）| ❌| ✔️ | MyEMS-zertifizierte industrielle Computerhardware |
| LoRa Radio Module (Data Acquisition and Remote Control）   | ❌| ✔️ | MyEMS-zertifiziertes LoRa-Hardwaregerät |
| Protocol for Uploading to Provincial Platform of On-line monitoring system for Key Energy-Consuming Unit | ❌     | ✔️        |                      |
| 3rd Party Systems Integration Service | ❌        | ✔️        | Kundenspezifische Entwicklung |
| Online software training         | ❌             | ✔️        |                      |
| Face to face software training   | ❌             | ✔️        |                      |
| Online Community Customer Support| ✔️              | ✔️        |                      |
| Email Customer Support           | ❌             | ✔️        |                      |
| Telephone Customer Support       | ❌             | ✔️        |                      |
| WeChat Customer Support          | ❌             | ✔️        |                      |
| Remote Desktop Customer Support  | ❌             | ✔️        |                      |
| Onsite Customer Support          | ❌             | ✔️        |                      |
| Bidding Support Service          | ❌             | ✔️        |                      |
| Customize Support Service        | ❌             | ✔️        |                      |


## MyEMS Bildschirmfoto
![MyEMS Space EnergyCategory1](/docs/images/myems-space-energycategory1.gif)
![MyEMS Space EnergyCategory2](/docs/images/myems-space-energycategory2.gif)
![MyEMS Space EnergyCategory3](/docs/images/myems-space-energycategory3.gif)
![MyEMS Großbild-Dashboard](/docs/images/myems-large-screen-dashboard.gif)


## MyEMS Straßenkarte

[Community Edition Straßenkarte](https://github.com/orgs/MyEMS/projects)


## MyEMS Spiegel

[1]. [http://github.com/MyEMS/myems](http://github.com/MyEMS/myems)
  
[2]. [http://gitee.com/myems/myems](http://gitee.com/myems/myems)

[3]. [http://bitbucket.org/myems/myems](http://bitbucket.org/myems/myems)

[4]. [https://gitlab.com/myems/myems](https://gitlab.com/myems/myems)

