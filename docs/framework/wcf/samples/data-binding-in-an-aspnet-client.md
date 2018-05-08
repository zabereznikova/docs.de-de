---
title: Datenbindung in einem ASP.NET-Client
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: c0f3cbb08f0078bf364ef720635f7afda3257611
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-binding-in-an-aspnet-client"></a>Datenbindung in einem ASP.NET-Client
Dieses Beispiel veranschaulicht das Binden von Daten von einem normalen Windows Communication Foundation (WCF)-Dienst in einer Web Forms-Anwendung zurückgegeben.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einer Web&#160;Forms-Clientanwendung, auf die über einen Browser zugegriffen werden kann, und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der von Internetinformationsdiensten (IIS) gehostet wird.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Auf der ASPX-Seite des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Clients wird ein DataGrid-Websteuerelement definiert, das die grafische Darstellung der vom Dienst zurückgegebenen Daten enthält. Der Code auf der ASPX-Seite ruft den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst auf, um Wetterdaten abzurufen, und gibt diese Daten in ein Array von `WeatherData`-Objekten aus. Im DataGrid wird angegeben, von wo die Daten abgerufen werden sollen, indem die `DataSource`-Eigenschaft auf dieses Array festgelegt wird. Die Datenbindung erfolgt durch einen Aufruf der `DataBind`-Methode des DataGrid. Sämtliche dieser Code befinden sich innerhalb der.`aspx` Seite `Page_Load` Methode, sodass jedes Mal der Benutzer die Browserseite, die Daten aktualisiert wird im DataGrid ebenfalls aktualisiert.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Der Client dieses Beispiels ist eine Website, die unter einem Development Web Server ausgeführt wird. Um den Development Webserver zu starten, geben Sie Folgendes an der Eingabeaufforderung: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Navigieren Sie zu http://localhost:8000/client. Um dieses Beispiel computerübergreifend auszuführen, ersetzen Sie in der Datei Web.config des Clients alle Verweise auf `localhost` durch den Computernamen des Servers.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a>Siehe auch
