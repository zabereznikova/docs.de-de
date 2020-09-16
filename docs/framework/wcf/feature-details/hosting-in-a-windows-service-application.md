---
title: Hosten in einer Windows-Dienstanwendung
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: cb952cfcd670a790033fbec70de00a4db2541237
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555847"
---
# <a name="hosting-in-a-windows-service-application"></a>Hosten in einer Windows-Dienstanwendung
Windows-Dienste (früher Windows NT-Dienste) bieten ein Prozessmodell, das besonders für Anwendungen geeignet ist, die sich in ausführbaren Dateien mit langer Laufzeit befinden müssen und keinerlei Benutzeroberfläche anzeigen. Die Prozesslebensdauer einer Windows-Dienstanwendung wird vom Dienststeuerungs-Manager (Service Control Manager, SCM) verwaltet, mit dem Sie Windows-Dienstanwendungen starten, beenden und anhalten können. Sie können einen Windows-Dienst Prozess so konfigurieren, dass er beim Starten des Computers automatisch gestartet wird. Dadurch wird er zu einer geeigneten Hostingumgebung für "Always on"-Anwendungen. Weitere Informationen zu Windows-Dienst Anwendungen finden Sie unter [Windows-Dienst Anwendungen](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Anwendungen, die WCF-Dienste (Long-Running Windows Communication Foundation) hosten, haben viele Merkmale mit Windows-Diensten. Bei WCF-Diensten handelt es sich insbesondere um ausführbare Server Dateien mit langer Ausführungsdauer, die nicht direkt mit dem Benutzer interagieren und daher keine Form von Benutzeroberflächen implementieren. Daher ist das Hosting von WCF-Diensten innerhalb einer Windows-Dienst Anwendung eine Option zum entwickeln robuster, lang laufender WCF-Anwendungen.  
  
 Häufig müssen WCF-Entwickler entscheiden, ob Ihre WCF-Anwendung in einer Windows-Dienst Anwendung oder in der Host Umgebung von Internetinformationsdienste (IIS) oder Windows Process Activation Service (was) gehostet werden soll. Unter folgenden Bedingungen sollen Sie die Verwendung von Windows-Dienstanwendungen in Erwägung ziehen:  
  
- Die Anwendung erfordert explizite Aktivierung. Beispielsweise sollten Sie Windows-Dienste verwenden, wenn die Anwendung automatisch beim Serverstart gestartet werden soll, statt dynamisch als Antwort auf die erste eingehende Nachricht.  
  
- Der Prozess, der die Anwendung hostet, muss nach dem Start weiterhin ausgeführt werden. Nach dem Start wird ein Windows-Dienstprozess solange ausgeführt, bis er explizit von einem Serveradministrator über den Dienststeuerungs-Manager beendet wird. In IIS oder WAS gehostete Anwendungen können dynamisch gestartet und beendet werden, um die Systemressourcen optimal zu nutzen. Anwendungen, die explizite Steuerung während der gesamten Lebensdauer ihres Hostingprozesses erfordern, sollten Windows-Dienste anstelle von IIS oder WAS verwenden.  
  
- Der WCF-Dienst muss unter Windows Server 2003 ausgeführt werden und andere Transporte als HTTP verwenden. Unter Windows Server 2003 ist die IIS 6,0-Hostingumgebung ausschließlich auf die HTTP-Kommunikation beschränkt. Windows-Dienst Anwendungen unterliegen dieser Einschränkung nicht und können sämtliche von WCF unterstützten WCF-Dienste verwenden, einschließlich net. TCP, net. Pipe und net. MSMQ.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>So hosten Sie WCF innerhalb einer Windows-Dienstanwendung  
  
1. Erstellen Sie eine Windows-Dienstanwendung. Mit den Klassen im <xref:System.ServiceProcess>-Namespace können Sie Windows-Dienstanwendungen in verwaltetem Code schreiben. Diese Anwendung muss eine Klasse einschließen, die von <xref:System.ServiceProcess.ServiceBase> erbt.  
  
2. Verknüpfen Sie die Lebensdauer der WCF-Dienste mit der Lebensdauer der Windows-Dienst Anwendung. In der Regel möchten Sie, dass WCF-Dienste, die in einer Windows-Dienst Anwendung gehostet werden, beim Start des Hostingdiensts aktiviert werden, die Überwachung auf Nachrichten beenden, wenn der Hostingdienst angehalten wird, und den Hostingprozess beenden, wenn der WCF-Dienst Dies kann folgendermaßen erfüllt werden:  
  
    - Überschreiben Sie <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, um eine oder mehrere Instanzen von <xref:System.ServiceModel.ServiceHost> zu öffnen. Eine einzelne Windows-Dienst Anwendung kann mehrere WCF-Dienste hosten, die als Gruppe gestartet und beendet werden.  
  
    - <xref:System.ServiceProcess.ServiceBase.OnStop%2A>Überschreiben Sie, um <xref:System.ServiceModel.Channels.CommunicationObject.Closed> für <xref:System.ServiceModel.ServiceHost> alle laufenden WCF-Dienste aufzurufen, die während gestartet wurden <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> .  
  
    - Abonnieren Sie das <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>-Ereignis von <xref:System.ServiceModel.ServiceHost>, und verwenden Sie die <xref:System.ServiceProcess.ServiceController>-Klasse, um die Windows-Dienstanwendung im Fehlerfall zu beenden.  
  
     Windows-Dienst Anwendungen, die WCF-Dienste hosten, werden auf die gleiche Weise wie Windows-Dienst Anwendungen bereitgestellt und verwaltet, die WCF nicht verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceProcess>
- [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](https://go.microsoft.com/fwlink/?LinkId=94875)
- [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Windows-Diensthost](../samples/windows-service-host.md)
- [Programmierarchitektur für Dienstanwendungen](https://go.microsoft.com/fwlink/?LinkId=94876)
- [Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))
