---
title: Datenbindung in einem ASP.NET-Client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18d133b8eb5bef9e6e9152ef856265c1cbe18b51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="data-binding-in-an-aspnet-client"></a>Datenbindung in einem ASP.NET-Client
Dieses Beispiel veranschaulicht, wie Daten, die von einem typischen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst zurückgegeben wurden, in einer Web Forms-Anwendung gebunden werden.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einer Web&#160;Forms-Clientanwendung, auf die über einen Browser zugegriffen werden kann, und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der von Internetinformationsdiensten (IIS) gehostet wird.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Auf der ASPX-Seite des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Clients wird ein DataGrid-Websteuerelement definiert, das die grafische Darstellung der vom Dienst zurückgegebenen Daten enthält. Der Code auf der ASPX-Seite ruft den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst auf, um Wetterdaten abzurufen, und gibt diese Daten in ein Array von `WeatherData`-Objekten aus. Im DataGrid wird angegeben, von wo die Daten abgerufen werden sollen, indem die `DataSource`-Eigenschaft auf dieses Array festgelegt wird. Die Datenbindung erfolgt durch einen Aufruf der `DataBind`-Methode des DataGrid. Sämtliche dieser Code befinden sich innerhalb der.`aspx` Seite `Page_Load` Methode, sodass jedes Mal der Benutzer die Browserseite, die Daten aktualisiert wird im DataGrid ebenfalls aktualisiert.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Der Client dieses Beispiels ist eine Website, die unter einem Development Web Server ausgeführt wird. Um den Development Webserver zu starten, geben Sie Folgendes an der Eingabeaufforderung: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Wechseln Sie dann zu http://localhost:8000/client. Um dieses Beispiel computerübergreifend auszuführen, ersetzen Sie in der Datei Web.config des Clients alle Verweise auf `localhost` durch den Computernamen des Servers.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a>Siehe auch
