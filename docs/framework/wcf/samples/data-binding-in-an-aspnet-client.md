---
title: Datenbindung in einem ASP.NET-Client
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: 07e03a4580795b3424f63cec8f93fea2039b6733
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339410"
---
# <a name="data-binding-in-an-aspnet-client"></a>Datenbindung in einem ASP.NET-Client
In diesem Beispiel wird veranschaulicht, wie zum Binden von Daten, die von einem typischen Windows Communication Foundation (WCF)-Dienst in einer Web Forms-Anwendung zurückgegeben wird.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einer Web Forms-Anwendung, die über einen Browser und einen WCF-Dienst von IIS (Internetinformationsdienste) gehostet.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Auf der ASPX-Seite des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Clients wird ein DataGrid-Websteuerelement definiert, das die grafische Darstellung der vom Dienst zurückgegebenen Daten enthält. Code auf der ASPX-Seite ruft den WCF-Dienst für die Wetterdaten auf und gibt diese Daten in ein Array von `WeatherData` Objekte. Im DataGrid wird angegeben, von wo die Daten abgerufen werden sollen, indem die `DataSource`-Eigenschaft auf dieses Array festgelegt wird. Die Datenbindung erfolgt durch einen Aufruf der `DataBind`-Methode des DataGrid. All dieser Code befindet sich innerhalb der.`aspx` Seite `Page_Load` Methode, sodass jedes Mal der Benutzer die Browserseite, die Daten aktualisiert, die in das DataGrid-Steuerelement aktualisiert wird.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Der Client dieses Beispiels ist eine Website, die unter einem Development Web Server ausgeführt wird. Um den Development Webserver zu starten, geben Sie Folgendes an der Eingabeaufforderung: `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Navigieren Sie dann zum `http://localhost:8000/client`. Um dieses Beispiel computerübergreifend auszuführen, ersetzen Sie in der Datei Web.config des Clients alle Verweise auf `localhost` durch den Computernamen des Servers.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
