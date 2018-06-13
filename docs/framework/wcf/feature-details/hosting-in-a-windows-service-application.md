---
title: Hosten in einer Windows-Dienstanwendung
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: e440961055ccd40bf56b4b88ea73d167f1903245
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492231"
---
# <a name="hosting-in-a-windows-service-application"></a>Hosten in einer Windows-Dienstanwendung
Windows-Dienste (früher Windows NT-Dienste) bieten ein Prozessmodell, das besonders für Anwendungen geeignet ist, die sich in ausführbaren Dateien mit langer Laufzeit befinden müssen und keinerlei Benutzeroberfläche anzeigen. Die Prozesslebensdauer einer Windows-Dienstanwendung wird vom Dienststeuerungs-Manager (Service Control Manager, SCM) verwaltet, mit dem Sie Windows-Dienstanwendungen starten, beenden und anhalten können. Sie können ein Windows-Dienstprozess für den automatischen start beim Starten des Computers somit eine angemessene Hostingumgebung für "immer aktiviert" Anwendungen konfigurieren. Weitere Informationen zu Windows-dienstanwendungen, finden Sie unter [Windows-Dienstanwendungen](http://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Anwendungen, die lang andauernde Windows Communication Foundation (WCF)-Dienste hosten haben viele gemeinsamkeiten mit Windows-Dienste. WCF-Dienste sind insbesondere Serverdateien mit langer, die interagieren nicht direkt mit dem Benutzer und daher keinerlei Benutzeroberfläche nicht implementiert. Daher ist das Hosten von WCF-Diensten innerhalb einer Windows-dienstanwendung eine Option zum Erstellen robuster und lang andauernde, WCF-Clientanwendungen.  
  
 Häufig müssen erfahrenen Entwicklern von WCF entscheiden, ob ihre WCF-Anwendung in einer Windows-dienstanwendung oder in der hostumgebung (Internet Information Services, IIS) oder Windows Process Activation Service (WAS) hosten. Unter folgenden Bedingungen sollen Sie die Verwendung von Windows-Dienstanwendungen in Erwägung ziehen:  
  
-   Die Anwendung erfordert explizite Aktivierung. Beispielsweise sollten Sie Windows-Dienste verwenden, wenn die Anwendung automatisch beim Serverstart gestartet werden soll, statt dynamisch als Antwort auf die erste eingehende Nachricht.  
  
-   Der Prozess, der die Anwendung hostet, muss nach dem Start weiterhin ausgeführt werden. Nach dem Start wird ein Windows-Dienstprozess solange ausgeführt, bis er explizit von einem Serveradministrator über den Dienststeuerungs-Manager beendet wird. In IIS oder WAS gehostete Anwendungen können dynamisch gestartet und beendet werden, um die Systemressourcen optimal zu nutzen. Anwendungen, die explizite Steuerung während der gesamten Lebensdauer ihres Hostingprozesses erfordern, sollten Windows-Dienste anstelle von IIS oder WAS verwenden.  
  
-   Der WCF-Dienst muss unter Windows Server 2003 ausführen und andere Transportoptionen als HTTP verwenden. Auf Windows&#160;Server&#160;2003 ist die [!INCLUDE[iis601](../../../../includes/iis601-md.md)]-Hostumgebung auf HTTP-Kommunikation beschränkt. Windows-dienstanwendungen fallen nicht unter diese Beschränkung und können Transport WCF unterstützt werden, darunter net.tcp, net.pipe und net.msmq.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>So hosten Sie WCF innerhalb einer Windows-Dienstanwendung  
  
1.  Erstellen Sie eine Windows-Dienstanwendung. Mit den Klassen im <xref:System.ServiceProcess>-Namespace können Sie Windows-Dienstanwendungen in verwaltetem Code schreiben. Diese Anwendung muss eine Klasse einschließen, die von <xref:System.ServiceProcess.ServiceBase> erbt.  
  
2.  Verknüpfen Sie die Lebensdauer der WCF-Dienste, von der Lebensdauer der Windows-dienstanwendung. In der Regel möchten Sie die WCF-Diensten in einer Windows-dienstanwendung werden aktiviert, beim Starten des Hostingdienst, Beenden der Überwachung für Nachrichten beim hosting-Dienst beendet, und der Hostprozess heruntergefahren wird, wenn der WCF-Dienst ein Fehler auftritt. Dies kann folgendermaßen erfüllt werden:  
  
    -   Überschreiben Sie <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, um eine oder mehrere Instanzen von <xref:System.ServiceModel.ServiceHost> zu öffnen. Eine einzelne Windows-dienstanwendung kann mehrere WCF-Dienste hosten, die starten und beenden, die als Gruppe.  
  
    -   Überschreiben Sie <xref:System.ServiceProcess.ServiceBase.OnStop%2A> Aufrufen <xref:System.ServiceModel.Channels.CommunicationObject.Closed> auf die <xref:System.ServiceModel.ServiceHost> alle ausgeführten WCF-Dienste, die während der gestartet wurden <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    -   Abonnieren Sie das <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>-Ereignis von <xref:System.ServiceModel.ServiceHost>, und verwenden Sie die <xref:System.ServiceProcess.ServiceController>-Klasse, um die Windows-Dienstanwendung im Fehlerfall zu beenden.  
  
     Windows-dienstanwendungen, die WCF-Dienste gehostet werden bereitgestellt und auf die gleiche Weise verwaltet werden, da Windows-dienstanwendungen, die nicht vornehmen von WCF verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceProcess>  
 [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](http://go.microsoft.com/fwlink/?LinkId=94875)  
 [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Windows-Diensthost](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [Programmierarchitektur für Dienstanwendungen](http://go.microsoft.com/fwlink/?LinkId=94876)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
