---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 944eb8f2bd907308e60525f8917fcad826caa472
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932065"
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting-Integrationsbeispiel
In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht. Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen. Webrouting ermöglicht es, den Entwickler zum Erstellen von virtueller Adressen für HTTP, klicken Sie dann wieder die tatsächlichen WCF-Diensten zugeordnet sind. Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten. In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden. 

> [!NOTE]
>  Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.  
  
In diesem Beispiel verwendet WCF, um zwei RSS-Feeds zu erstellen: eine `movies` feed und ein `channels` feed. Die URLs zur Aktivierung der Dienste enthalten keine Erweiterung und registriert sind, der `Application_Start` Methode der `Global` abgeleitete Klasse die <xref:System.Web.HttpApplication> Klasse.  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nur in IIS (Internetinformationsdienste) 7.0 und höher, wie IIS 6.0 verwendet eine andere Methode für die Unterstützung von URLs ohne Erweiterung.  

#### <a name="to-download-this-sample"></a>Dieses Beispiel herunterladen
  
In diesem Beispiel möglicherweise bereits auf Ihrem Computer installiert werden. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.  
  
2.  Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.  
  
     Eine Verzeichnisliste für das Beispiel wird angezeigt. Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.  
  
3.  Fügen Sie in der Adressleiste `movies` an die URL so, dass die It liest `http://localhost:[port]/movies` und drücken Sie EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
4.  Fügen Sie in der Adressleiste `channels` an die URL ein, das ist also Lesevorgänge `http://localhost:[port]/channels` und drücken Sie EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
5.  Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
     Wenn der Entwicklungsserver nicht beendet wurde, mit der rechten Maustaste in des Symbols im Infobereich, und wählen Sie **beenden**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird  
  
1.  Öffnen Sie die Datei webroutingintegration.sln in mit Visual Studio.  
  
2.  Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.  
  
    1.  Im IIS-Manager mit der rechten Maustaste die **Default Web Site** , und wählen Sie **Hinzufügen einer Anwendung**.  
  
    2.  Für die **Alias**, geben Sie in `WebRoutingIntegration`.  
  
    3.  Für die **physischer Pfad**, wählen Sie den Ordner "Service" innerhalb des Projekts.  
  
    4.  Drücken Sie **OK**.  
  
4.  Starten Sie die Anwendung, indem Sie mit der rechten Maustaste in der Web-Anwendung und auswählen **-Anwendung verwalten** und dann **Durchsuchen**.  
  
5.  Fügen Sie in der Adressleiste `movies` an die URL ein, das ist also Lesevorgänge `http://localhost:[port]/movies` und drücken Sie EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
6.  Fügen Sie in der Adressleiste `channels` an die URL ein, das ist also Lesevorgänge `http://localhost:[port]/channels` und drücken Sie EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
7.  Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
 In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.  
  
> [!NOTE]
>  Sie müssen die Version des Standardanwendungspools auf Aktualisieren [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] , wenn sie auf Version 2 festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting- und-persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
