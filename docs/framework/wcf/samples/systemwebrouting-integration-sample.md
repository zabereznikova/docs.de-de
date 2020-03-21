---
title: SystemWebRouting-Integrationsbeispiel
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143953"
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting-Integrationsbeispiel
In diesem Beispiel wird die Integration der Hostebene in die Klassen im <xref:System.Web.Routing>-Namespace veranschaulicht. Mit den Klassen im <xref:System.Web.Routing>-Namespace können Anwendungen URLs verwenden, die einer physischen Ressource nicht direkt entsprechen. Mithilfe des Webroutings kann der Entwickler virtuelle Adressen für HTTP erstellen, die dann den tatsächlichen WCF-Diensten zugeordnet werden. Dies ist nützlich, wenn ein WCF-Dienst gehostet werden muss, ohne dass eine physische Datei oder Ressource erforderlich ist, oder wenn auf Dienste mit URLs zugegriffen werden muss, die keine Dateierweiterung wie .html oder .aspx enthalten. In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Web.Routing.RouteTable>-Klasse virtuelle URIs erstellt werden können, die in global.asax definierten, ausgeführten Diensten zugeordnet werden.

> [!NOTE]
> Die Klassen im <xref:System.Web.Routing>-Namespace können nur für Dienste verwendet werden, die über HTTP gehostet werden.  
  
In diesem Beispiel werden WCF verwendet, `movies` um zwei `channels` RSS-Feeds zu erstellen: einen Feed und einen Feed. Die URLs zum Aktivieren der Dienste enthalten keine `Application_Start` Erweiterung und `Global` werden in <xref:System.Web.HttpApplication> der Methode der von der Klasse abgeleiteten Klasse registriert.  
  
> [!NOTE]
> Dieses Beispiel funktioniert nur in Internet Information Services (IIS) 7.0 und höher, da IIS 6.0 eine andere Methode zur Unterstützung von URLs ohne Erweiterung verwendet.  

#### <a name="to-download-this-sample"></a>So laden Sie dieses Beispiel herunter
  
Dieses Beispiel ist möglicherweise bereits auf Ihrem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  

`<InstallDrive>:\WF_WCF_Samples`  

 Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie mit Visual Studio die Datei WebRoutingIntegration.sln.  
  
2. Drücken Sie F5, um die Projektmappe auszuführen und den Webentwicklungsserver zu starten.  
  
     Eine Verzeichnisliste für das Beispiel wird angezeigt. Beachten Sie, dass es keine Dateien mit der Dateierweiterung SVC gibt.  
  
3. Fügen Sie `movies` in der Adressleiste der URL `http://localhost:[port]/movies` hinzu, sodass sie die EINGABETASTE liest und drückt.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
4. Fügen Sie `channels` in der Adressleiste der URL `http://localhost:[port]/channels` hinzu, das heißt leset, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
5. Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
     Wenn der Entwicklungsserver nicht beendet wurde, klicken Sie mit der rechten Maustaste auf das Symbol für den Benachrichtigungsbereich, und wählen Sie **Stopp**aus.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>So verwenden Sie dieses Beispiel, wenn es in IIS gehostet wird  
  
1. Öffnen Sie mit Visual Studio die Datei WebRoutingIntegration.sln.  
  
2. Erstellen Sie das Projekt, indem Sie STRG+UMSCHALT+B drücken.  
  
3. Erstellen Sie eine Webanwendung im Internetinformationsdienste-Manager.  
  
    1. Klicken Sie in IIS Manager mit der rechten Maustaste auf die **Standardwebsite,** und wählen Sie **Anwendung hinzufügen**aus.  
  
    2. Geben **alias**Sie für `WebRoutingIntegration`den Alias ein in .  
  
    3. Wählen Sie für den **physischen Pfad**den Dienstordner innerhalb des Projekts aus.  
  
    4. Klicken Sie auf **OK**.  
  
4. Starten Sie die Anwendung, indem Sie mit der rechten Maustaste auf die Webanwendung klicken und **Anwendung verwalten** auswählen und dann **durchsuchen**.  
  
5. Fügen Sie `movies` in der Adressleiste der URL `http://localhost:[port]/movies` hinzu, das heißt leset, und drücken Sie die EINGABETASTE.  
  
     Der Filmfeed (movies) wird im Browser angezeigt.  
  
6. Fügen Sie `channels` in der Adressleiste der URL `http://localhost:[port]/channels` hinzu, das heißt leset, und drücken Sie die EINGABETASTE.  
  
     Der Channelfeed wird im Browser angezeigt.  
  
7. Schließen Sie den Webbrowser, indem Sie ALT+F4 drücken.  
  
 In diesem Beispiel wird gezeigt, dass die Hostebene mit den Klassen im <xref:System.Web.Routing>-Namespace eingesetzt werden kann, um die Anforderungen von Diensten zu routen, die über HTTP gehostet werden.  
  
> [!NOTE]
> Sie müssen die Standardversion des Anwendungspools auf .NET Framework 4 aktualisieren, wenn sie auf Version 2 festgelegt ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Hosting- und -Persistenzbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
