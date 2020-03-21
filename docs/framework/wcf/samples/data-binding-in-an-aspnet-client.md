---
title: Datenbindung in einem ASP.NET-Client
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: c068c1cab5a5b9dad75e781e58076f4066a3b2a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145006"
---
# <a name="data-binding-in-an-aspnet-client"></a>Datenbindung in einem ASP.NET-Client
In diesem Beispiel wird veranschaulicht, wie Daten gebunden werden, die von einem typischen Windows Communication Foundation (WCF)-Dienst in einer Web Forms-Anwendung zurückgegeben werden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einer Web Forms-Clientanwendung, auf die über einen Browser zugegriffen werden kann, und einem WCF-Dienst, der von Internet Informationsdiensten (Internet Information Services, IIS) gehostet wird.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Auf der Seite ASP.NET Client .aspx wird ein DataGrid-Websteuerelement definiert, das die grafische Darstellung der vom Dienst zurückgegebenen Daten enthält. Code auf der ASPX-Seite ruft den WCF-Dienst für Wetterdaten auf und gibt die Daten an ein Array von `WeatherData` Objekten zurück. Im DataGrid wird angegeben, von wo die Daten abgerufen werden sollen, indem die `DataSource`-Eigenschaft auf dieses Array festgelegt wird. Die Datenbindung erfolgt durch einen Aufruf der `DataBind`-Methode des DataGrid. Der gesamte Code ist im enthalten.`aspx` Die Methode `Page_Load` der Seite, sodass die Daten jedes Mal, wenn der Benutzer die Browserseite aktualisiert, im DataGrid aktualisiert werden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Der Client dieses Beispiels ist eine Website, die unter einem Development Web Server ausgeführt wird. Um den Entwicklungswebserver zu starten, geben `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`Sie an der Eingabeaufforderung Folgendes ein: . Navigieren Sie `http://localhost:8000/client`dann zu . Um dieses Beispiel computerübergreifend auszuführen, ersetzen Sie in der Datei Web.config des Clients alle Verweise auf `localhost` durch den Computernamen des Servers.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
