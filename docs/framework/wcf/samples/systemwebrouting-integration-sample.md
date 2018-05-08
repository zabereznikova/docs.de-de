---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 43785f84cb3852a35f1ed3bd555287842455a89b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting-Integrationsbeispiel
In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht. Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen. Webrouting ermöglicht es dem Entwickler, virtuelle Adressen für HTTP zu erstellen, die danach erneut tatsächlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten zugeordnet werden. Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten. In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden. 

> [!NOTE]
>  Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.  
  
In diesem Beispiel verwendet die WCF zum Erstellen von zwei RSS-Feeds: ein `movies` feed und ein `channels` feed. Die URLs zur Aktivierung der Dienste enthalten keine Erweiterung und registriert sind, der `Application_Start` Methode der `Global` abgeleitete Klasse die <xref:System.Web.HttpApplication> Klasse.  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nur in Internetinformationsdienste (IIS) 7.0 und höher, wie IIS 6.0 verwendet eine andere Methode für die Unterstützung von URLs ohne Erweiterung.  

#### <a name="to-download-this-sample"></a>Dieses Beispiel herunterladen
  
In diesem Beispiel möglicherweise bereits auf Ihrem Computer installiert werden. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.  
  
2.  Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.  
  
     Eine Verzeichnisliste für das Beispiel wird angezeigt. Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.  
  
3.  Fügen Sie in der Adressleiste `movies` an die URL so, dass die It liest http://localhost:[Port] / Movies und drücken Sie EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
4.  Fügen Sie in der Adressleiste `channels` an die URL, also Lesevorgänge http://localhost:[Port] / channels lautet, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
5.  Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
     Wenn der Entwicklungsserver nicht beendet wurde, mit der rechten Maustaste das Symbol im Infobereich, und wählen Sie **beenden**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird  
  
1.  Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.  
  
2.  Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.  
  
    1.  Mit der rechten Maustaste im IIS-Manager, klicken Sie auf die **Default Web Site** , und wählen Sie **Hinzufügen einer Anwendung**.  
  
    2.  Für die **Alias**, geben Sie in `WebRoutingIntegration`.  
  
    3.  Für die **physischen Pfad**, wählen Sie den Dienstordner im Projekt.  
  
    4.  Press **OK**.  
  
4.  Starten Sie die Anwendung, indem Sie die Web-Anwendung mit der rechten Maustaste und auswählen **-Anwendung verwalten** und dann **Durchsuchen**.  
  
5.  Fügen Sie in der Adressleiste `movies` an die URL, also Lesevorgänge http://localhost:[Port] / Movies und drücken Sie EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
6.  Fügen Sie in der Adressleiste `channels` an die URL, also Lesevorgänge http://localhost:[Port] / channels lautet, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
7.  Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
 In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.  
  
> [!NOTE]
>  Sie müssen die Version des Standardanwendungspools auf Aktualisieren [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] , wenn sie auf Version 2 festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
