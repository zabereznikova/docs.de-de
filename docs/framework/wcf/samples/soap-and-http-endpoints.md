---
title: SOAP- und HTTP-Endpunkte
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: f10b1aa4514aee50c0c0d17cabdb9516a3ca7584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144018"
---
# <a name="soap-and-http-endpoints"></a>SOAP- und HTTP-Endpunkte
In diesem Beispiel wird veranschaulicht, wie Sie einen RPC-basierten Dienst implementieren und im SOAP-Format und im POX-Format (Plain Old XML) mithilfe des WCF-Webprogrammierungsmodells verfügbar machen. Weitere Informationen zur HTTP-Bindung für den Dienst finden Sie im Beispiel des [Basis-HTTP-Diensts.](../../../../docs/framework/wcf/samples/basic-http-service.md) Dieses Beispiel befasst sich mit den Details der Bereitstellung des gleichen Diensts über SOAP und HTTP, allerdings mit unterschiedlichen Bindungen.  
  
## <a name="demonstrates"></a>Zeigt  
 Offenlegen eines RPC-Dienstes über SOAP und HTTP mithilfe von WCF.  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel besteht aus zwei Komponenten: einem Webanwendungsprojekt (Service), das einen WCF-Dienst enthält, und einer Konsolenanwendung (Client), die Dienstvorgänge mithilfe von SOAP- und HTTP-Bindungen aufruft.  
  
 Der WCF-Dienst macht`GetData` zwei `PutData` Vorgänge verfügbar – und – die die Zeichenfolge wiedergeben, die als Eingabe übergeben wurde. Die Dienstvorgänge werden mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> kommentiert. Diese Attribute steuern die HTTP-Projektion dieser Vorgänge. Außerdem werden sie mit <xref:System.ServiceModel.OperationContractAttribute> kommentiert, sodass sie über SOAP-Bindungen verfügbar gemacht werden können. Die `PutData`-Methode des Diensts löst eine <xref:System.ServiceModel.Web.WebFaultException> aus, die mithilfe des HTTP-Statuscodes über HTTP zurückgesendet und als SOAP-Fehler über SOAP zurückgesendet wird.  
  
 Die Datei Web.config konfiguriert den WCF-Dienst mit 3 Endpunkten:  
  
- Der ~/service.svc/mex-Endpunkt, der die Dienstmetadaten für den Zugriff durch SOAP-basierte Clients verfügbar macht.  
  
- Der ~/service.svc/http-Endpunkt, der es Clients ermöglicht, über die HTTP-Bindung auf den Dienst zuzugreifen.  
  
- Der ~/service.svc/soap-Endpunkt, der es den Clients ermöglicht, über die SOAP über HTTP-Bindung auf den Dienst zuzugreifen.  
  
 Der HTTP-Endpunkt ist mit `webHttp` einem <> `helpEnabled` Standardendpunkt konfiguriert, der auf `true`festgelegt ist. Als Ergebnis stellt der Dienst eine XHTML-basierte Hilfeseite unter ~/service.svc/http/help bereit, mit der HTTP-basierte Clients auf den Dienst zugreifen können.  
  
 Das Clientprojekt veranschaulicht den Zugriff auf den Dienst mithilfe eines SOAP-Proxys <xref:System.Net.WebClient>(generiert über **die Dienstreferenz hinzufügen**) und den Zugriff auf den Dienst mithilfe von .  
  
 Das Beispiel besteht aus einem im Web gehosteten Dienst und einer Konsolenanwendung. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-run-the-sample"></a>Ausführen des Beispiels  
  
1. Öffnen Sie die Projektmappe für das Beispiel mit den SOAP- und HTTP-Endpunkten.  
  
2. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.  
  
3. Wenn es noch nicht geöffnet ist, drücken Sie STRG+W, S, um das **Projektmappen-Explorer-Fenster** zu öffnen.  
  
4. Klicken Sie im **Projektmappen-Explorer-Fenster** mit der rechten Maustaste auf das **Service-Projekt,** und platzieren Sie den Cursor über der Menüoption **Kontextmenü debuggen,** sodass das Kontextmenü **"Neue Instanz starten"** angezeigt wird. Klicken Sie auf **Neue Instanz starten**. Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5. Klicken Sie in den Fenstern des Projektmappen-Explorers mit der rechten Maustaste auf das Client-Projekt, und platzieren Sie den Cursor über die Menüoption **"Kontextmenü debuggen",** sodass das Kontextmenü **"Neue Instanz starten"** angezeigt wird. Klicken Sie auf **Neue Instanz starten**.  
  
6. Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.  
  
7. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
8. Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
9. Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.  
  
10. Klicken Sie im Windows-Benachrichtigungsbereich mit der rechten Maustaste auf das Symbol ASP.NET Entwicklungsserver, und wählen Sie im Kontextmenü **Stopp** aus.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
