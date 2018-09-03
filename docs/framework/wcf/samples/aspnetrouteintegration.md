---
title: AspNetRouteIntegration
ms.date: 03/30/2017
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
ms.openlocfilehash: 8d9a0710e5106cbc3d02a06e81f4f8ed9ae3e03b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475880"
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
In diesem Beispiel wird veranschaulicht, wie einen Windows Communication Foundation (WCF)-REST-Dienst mit ASP.NET-Routen gehostet wird. Die [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) -Beispiel zeigt eine selbst gehostete Version dieses Szenarios und die dienstimplementierung eingehend erläutert. In diesem Thema steht die ASP.NET-Integrationsfunktion im Vordergrund. Weitere Informationen zu ASP.NET finden Sie unter <xref:System.Web.Routing>.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der WCF-Dienst macht eine Auflistung von Kunden auf eine Ressource ressourcenorientierte/REST-Weise verfügbar. Genau wie einen SOAP-basierten WCF-Dienst kann der Dienst in ASP.NET mit einer SVC-Datei gehostet werden. Diese Vorgehensweise empfiehlt sich in HTTP-Szenarien jedoch häufig nicht, da sie erfordert, dass die URL für den Dienst .svc enthält. Darüber hinaus muss dafür eine SVC-Datei mit der Dienstbibliothek bereitgestellt werden. Diese Einschränkungen lassen sich vermeiden, wenn der Dienst mit ASP.NET-Routen gehostet wird, wie in diesem Beispiel gezeigt.  
  
 Im Beispiel wird der Dienst in ASP.NET gehostet, indem <xref:System.ServiceModel.Activation.ServiceRoute> in einer Global.asax-Datei hinzugefügt wird. Die <xref:System.ServiceModel.Activation.ServiceRoute> gibt den Typ des Diensts (in diesem Fall 'Service'), den Typ der für diesen Dienst zu verwendenden Diensthostfactory (in diesem Fall <xref:System.ServiceModel.Activation.WebServiceHostFactory>) und die HTTP-Basisadresse für den Dienst (in diesem Fall '~/Customers’) an.  
  
 Außerdem umfasst das Beispiel eine Web.config-Datei, die das <xref:System.Web.Routing.UrlRoutingModule> hinzufügt (um ASP.NET-Routen zu aktivieren) und die Konfiguration für den Dienst enthält. Vor allem die Konfiguration des WCF-Diensts konfiguriert, hat den Standardwert <xref:System.ServiceModel.Description.WebHttpEndpoint> , bei dem die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> auf `true`. Daher erstellt die WCF-Infrastruktur für eine automatische HTML-basierte Hilfeseite unter `http://localhost/Customers/help` , bereitstellt, finden Sie Informationen zum Erstellen von HTTP-Anforderungen für den Dienst und wie die HTTP-Antwort des Diensts – z. B. den Zugriff auf ein Beispiel dafür, wie der Kunde Details werden in XML und JSON dargestellt.  
  
 Indem der Client die Kundenauflistung (und, allgemeiner ausgedrückt, jede Ressource) auf diese Weise verfügbar macht, kann er mithilfe von URIs sowie HTTP `GET`, `PUT`, `DELETE` und `POST` auf einheitliche Weise mit einem Dienst interagieren.  
  
 Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, die Zugriff auf den Dienst mit anderen .NET Framework-Klassen wie die WCF-Kanalfactory und <xref:System.Net.WebClient>. In anderen Beispielen im SDK (z. B. die [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Beispiel und die [automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) Beispiel) zeigen, wie Sie diese Klassen verwenden, um die Kommunikation mit einem WCF-Dienst.  
  
 Dieses Beispiel besteht aus drei Projekten:  
  
 Dienst  
 Ein Webanwendungsprojekt einschließlich WCF-HTTP-Dienst, der in ASP.NET gehostet wird.  
  
 Client  
 Ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.  
  
 Allgemein  
 Eine freigegebene Bibliothek, die den vom Client und vom Dienst verwendeten `Customer`-Typ enthält. Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe für das Beispiel der ASP.NET-Routenintegration in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Wenn sie nicht bereits geöffnet ist, drücken Sie "STRG + W, S" zum Öffnen der **Projektmappen-Explorer** Fenster.  
  
4.  Von der **Projektmappen-Explorer** mit der rechten Maustaste der Windows die **Service** Projekt, und platzieren Sie den Cursor über der **Debuggen** Kontextmenüoption, damit die **starten Neue Instanz** Kontextmenü wird angezeigt, und wählen Sie **neue Instanz starten**.  Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Von der **Projektmappen-Explorer** mit der rechten Maustaste der Windows die **Client** Projekt, und platzieren Sie den Cursor über der **Debuggen** Kontextmenüoption, damit die **neue starten Instanz** Kontextmenü wird angezeigt, und wählen Sie **neue Instanz starten**.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
7.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
8.  Drücken Sie UMSCHALT + F5, um das Debuggen des Diensts beenden, in der Windows-Infobereich mit der Maustaste des ASP.NET Development Server-Symbols, und wählen Sie **beenden** aus dem Kontextmenü.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>Siehe auch
