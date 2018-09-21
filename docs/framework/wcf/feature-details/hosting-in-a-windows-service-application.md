---
title: Hosten in einer Windows-Dienstanwendung
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: 2b3935babec0c7cdc3ffca5dd11d693fdfee7a89
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46526333"
---
# <a name="hosting-in-a-windows-service-application"></a>Hosten in einer Windows-Dienstanwendung
Windows-Dienste (früher Windows NT-Dienste) bieten ein Prozessmodell, das besonders für Anwendungen geeignet ist, die sich in ausführbaren Dateien mit langer Laufzeit befinden müssen und keinerlei Benutzeroberfläche anzeigen. Die Prozesslebensdauer einer Windows-Dienstanwendung wird vom Dienststeuerungs-Manager (Service Control Manager, SCM) verwaltet, mit dem Sie Windows-Dienstanwendungen starten, beenden und anhalten können. Sie können eine Windows-Dienstprozess für den automatischen start beim Starten des Computers eine angemessene Hostingumgebung für "immer aktiviert"-Anwendungen erleichtert, konfigurieren. Weitere Informationen zu Windows-dienstanwendungen, finden Sie unter [Windows-Dienstanwendungen](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Anwendungen, die lang andauernde Windows Communication Foundation (WCF)-Dienste hosten, haben viele gemeinsamkeiten mit Windows-Diensten. WCF-Diensten handelt es sich insbesondere lang andauernde ausführbare Serverprogrammdateien, die nicht direkt mit dem Benutzer und daher nicht keinerlei Benutzeroberfläche implementieren. Daher ist das Hosten von WCF-Diensten innerhalb einer Windows-dienstanwendung eine Option zum Erstellen von robusten, lang andauernde, WCF-Anwendungen.  
  
 Häufig müssen WCF-Entwickler entscheiden, ob ihre WCF-Anwendung, die innerhalb einer Windows-dienstanwendung oder in der hostumgebung (Internet Information Services, IIS) oder Windows Process Activation Service (WAS) hosten. Unter folgenden Bedingungen sollen Sie die Verwendung von Windows-Dienstanwendungen in Erwägung ziehen:  
  
-   Die Anwendung erfordert explizite Aktivierung. Beispielsweise sollten Sie Windows-Dienste verwenden, wenn die Anwendung automatisch beim Serverstart gestartet werden soll, statt dynamisch als Antwort auf die erste eingehende Nachricht.  
  
-   Der Prozess, der die Anwendung hostet, muss nach dem Start weiterhin ausgeführt werden. Nach dem Start wird ein Windows-Dienstprozess solange ausgeführt, bis er explizit von einem Serveradministrator über den Dienststeuerungs-Manager beendet wird. In IIS oder WAS gehostete Anwendungen können dynamisch gestartet und beendet werden, um die Systemressourcen optimal zu nutzen. Anwendungen, die explizite Steuerung während der gesamten Lebensdauer ihres Hostingprozesses erfordern, sollten Windows-Dienste anstelle von IIS oder WAS verwenden.  
  
-   Der WCF-Dienst muss unter Windows Server 2003 ausführen und andere Transportoptionen als HTTP verwenden. Auf Windows&#160;Server&#160;2003 ist die [!INCLUDE[iis601](../../../../includes/iis601-md.md)]-Hostumgebung auf HTTP-Kommunikation beschränkt. Windows-dienstanwendungen können werden nicht in diese Einschränkung und alle Transport WCF unterstützt werden, einschließlich net.tcp, net.pipe und net.msmq.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>So hosten Sie WCF innerhalb einer Windows-Dienstanwendung  
  
1.  Erstellen Sie eine Windows-Dienstanwendung. Mit den Klassen im <xref:System.ServiceProcess>-Namespace können Sie Windows-Dienstanwendungen in verwaltetem Code schreiben. Diese Anwendung muss eine Klasse einschließen, die von <xref:System.ServiceProcess.ServiceBase> erbt.  
  
2.  Verknüpfen Sie die Lebensdauer der WCF-Dienste, mit der Lebensdauer der Windows-dienstanwendung. In der Regel sollten Sie die WCF-Diensten in einer Windows-dienstanwendung werden aktiviert, beim hosting-Dienst starten, beenden, warten auf Nachrichten des Hostingdiensts beendet, und der Hostprozess beendet wird, wenn der WCF-Dienst ein Fehler auftritt. Dies kann folgendermaßen erfüllt werden:  
  
    -   Überschreiben Sie <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, um eine oder mehrere Instanzen von <xref:System.ServiceModel.ServiceHost> zu öffnen. Eine einzelne Windows-dienstanwendung kann mehrere WCF-Dienste hosten, die starten und Beenden als Gruppe.  
  
    -   Außer Kraft setzen <xref:System.ServiceProcess.ServiceBase.OnStop%2A> aufzurufende <xref:System.ServiceModel.Channels.CommunicationObject.Closed> auf die <xref:System.ServiceModel.ServiceHost> alle ausgeführten WCF-Dienste, die während der gestarteten <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    -   Abonnieren Sie das <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>-Ereignis von <xref:System.ServiceModel.ServiceHost>, und verwenden Sie die <xref:System.ServiceProcess.ServiceController>-Klasse, um die Windows-Dienstanwendung im Fehlerfall zu beenden.  
  
     Windows-dienstanwendungen, die WCF-Dienste hosten bereitgestellt und auf die gleiche Weise verwaltet werden, wie Windows-dienstanwendungen, die keine von WCF verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceProcess>  
 [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](https://go.microsoft.com/fwlink/?LinkId=94875)  
 [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Windows-Diensthost](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [Programmierarchitektur für Dienstanwendungen](https://go.microsoft.com/fwlink/?LinkId=94876)  
 [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
