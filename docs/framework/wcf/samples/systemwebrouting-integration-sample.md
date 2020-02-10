---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: a91763e7dacb04a68cfea1079d55bbc1eda01668
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094890"
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting-Integrationsbeispiel
In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht. Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen. Die Verwendung von Webrouting ermöglicht es dem Entwickler, virtuelle Adressen für http zu erstellen, die dann wieder den eigentlichen WCF-Diensten zugeordnet werden. Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten. In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden. 

> [!NOTE]
> Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.  
  
In diesem Beispiel werden WCF verwendet, um zwei RSS-Feeds zu erstellen: einen `movies` Feed und einen `channels`-Feed. Die URLs zum Aktivieren der Dienste enthalten keine Erweiterung und werden in der `Application_Start`-Methode der `Global` Klasse, die von der <xref:System.Web.HttpApplication>-Klasse abgeleitet ist, registriert.  
  
> [!NOTE]
> Dieses Beispiel funktioniert nur in Internetinformationsdienste (IIS) 7,0 und höher, da IIS 6,0 eine andere Methode zur Unterstützung von URLs ohne Erweiterungen verwendet.  

#### <a name="to-download-this-sample"></a>So laden Sie dieses Beispiel herunter
  
Dieses Beispiel ist möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie in Visual Studio die Datei "webroutingintegration. sln".  
  
2. Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.  
  
     Eine Verzeichnisliste für das Beispiel wird angezeigt. Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.  
  
3. Fügen Sie in der Adressleiste `movies` der URL hinzu, damit `http://localhost:[port]/movies` gelesen wird, und drücken Sie die EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
4. Fügen Sie in der Adressleiste `channels` zur URL hinzu, damit Lesevorgänge `http://localhost:[port]/channels`, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
5. Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
     Wenn der Entwicklungs Server nicht beendet wurde, klicken Sie mit der rechten Maustaste auf das Benachrichtigungs Bereichs Symbol, und wählen Sie **Beenden**aus.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird  
  
1. Öffnen Sie in Visual Studio die Datei "webroutingintegration. sln".  
  
2. Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.  
  
3. Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.  
  
    1. Klicken Sie im IIS-Manager mit der rechten Maustaste auf die **Standard Website** , und wählen Sie **Anwendung hinzufügen**aus.  
  
    2. Geben Sie als **Alias**`WebRoutingIntegration`ein.  
  
    3. Wählen Sie für den **physischen Pfad**den Dienst Ordner innerhalb des Projekts aus.  
  
    4. Klicken Sie auf **OK**.  
  
4. Starten Sie die Anwendung, indem Sie mit der rechten Maustaste auf die Webanwendung klicken und **Anwendung verwalten** und dann **Durchsuchen**auswählen.  
  
5. Fügen Sie in der Adressleiste `movies` zur URL hinzu, damit Lesevorgänge `http://localhost:[port]/movies`, und drücken Sie die EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
6. Fügen Sie in der Adressleiste `channels` zur URL hinzu, damit Lesevorgänge `http://localhost:[port]/channels`, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
7. Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
 In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.  
  
> [!NOTE]
> Sie müssen die standardmäßige Anwendungs Poolversion auf .NET Framework 4 aktualisieren, wenn Sie auf Version 2 festgelegt ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Hosting-und persistenzbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
