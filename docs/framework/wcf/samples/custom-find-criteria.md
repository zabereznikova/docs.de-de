---
title: Benutzerdefinierte Suchkriterien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2723929-8829-424d-8015-a37ba2ab4f68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b57a9535b34441a8f1c86beeffa94046cf8944f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="custom-find-criteria"></a>Benutzerdefinierte Suchkriterien
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bereichsübereinstimmung mithilfe von Logik erstellt wird und wie ein benutzerdefinierter Suchdienst implementiert wird. Clients verfeinern mithilfe der Funktionalität für benutzerdefinierte Bereichsübereinstimmungen die vom System bereitgestellten Suchfunktionen der WCF-Suche und bauen diese zusätzlich aus. In diesem Beispiel wird folgendes Szenario behandelt:  
  
1.  Ein Client sucht nach einem Rechnerdienst.  
  
2.  Zur Verfeinerung der Suche muss der Client eine Regel für eine benutzerdefinierte Bereichsübereinstimmung verwenden.  
  
3.  Nach dieser Regel sendet ein Dienst eine Antwort an den Client, wenn sein Endpunkt mit einem der vom Client angegebenen Bereiche übereinstimmt.  
  
## <a name="demonstrates"></a>Veranschaulicht  
  
-   Es wird ein benutzerdefinierter Suchdienst erstellt.  
  
-   Es wird eine benutzerdefinierte Bereichsübereinstimmung nach Algorithmus implementiert.  
  
## <a name="discussion"></a>Diskussion  
 Der Client sucht nach Übereinstimmungskriterien "OR"-Typ. Ein Dienst sendet eine Antwort, wenn die Bereiche seiner Endpunkten mit einem der vom Client angegebenen Bereiche übereinstimmen. In diesem Fall sucht der Client nach einem Rechnerdienst mit einem der Bereiche in der folgenden Liste:  
  
1.  `net.tcp://Microsoft.Samples.Discovery/RedmondLocation`  
  
2.  `net.tcp://Microsoft.Samples.Discovery/SeattleLocation`  
  
3.  `net.tcp://Microsoft.Samples.Discovery/PortlandLocation`  
  
 Damit dies erzielt werden kann, weist der Client Dienste an, eine Regel für die benutzerdefinierte Bereichsübereinstimmung zu verwenden, indem eine benutzerdefinierte Bereichsübereinstimmung nach URI übergeben wird. Um die benutzerdefinierte Bereichsübereinstimmung zu erleichtern, muss vom Dienst ein benutzerdefinierter Suchdienst verwendet werden, der die Regel für die benutzerdefinierte Bereichsübereinstimmung nachvollziehen kann und die zugehörige Übereinstimmungslogik implementiert.  
  
 Öffnen Sie im Clientprojekt die Datei Program.cs. Beachten Sie, dass das `ScopeMatchBy`-Feld des `FindCriteria`-Objekts auf einen bestimmten URI festgelegt wird. Dieser Bezeichner wird an den Dienst gesendet. Wenn der Dienst diese Regel nicht versteht, ignoriert er die Suchanforderung des Clients.  
  
 Öffnen Sie das Dienstprojekt. Für die Implementierung des benutzerdefinierten Suchdiensts werden drei Dateien verwendet:  
  
1.  **AsyncResult.cs**: Dies ist die Implementierung der `AsyncResult` Suchmethoden erforderlich ist.  
  
2.  **CustomDiscoveryService.cs**: Diese Datei implementiert den benutzerdefinierten Ermittlungsdienst. Die Implementierung erweitert die <xref:System.ServiceModel.Discovery.DiscoveryService>-Klasse und überschreibt die erforderlichen Methoden. Beachten Sie die Implementierung der <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>-Methode. Die Methode überprüft, ob die benutzerdefinierte Bereichsübereinstimmung der Regel vom Client angegeben wurde. Dabei handelt es sich um den gleichen benutzerdefinierten URI, den der Client zuvor angegeben hat. Wenn die benutzerdefinierte Regel angegeben wird, folgt der Codepfad, der mit der "OR"-Übereinstimmungslogik implementiert.  
  
     Diese benutzerdefinierte Logik durchläuft sämtliche Bereiche der einzelnen Endpunkte, über die der Dienst verfügt. Wenn einer der Bereiche des Endpunkts mit einem der vom Client angegebenen Bereiche übereinstimmt, fügt der Suchdienst diesen Endpunkt der Antwort hinzu, die an den Client zurückgesendet wird.  
  
3.  **CustomDiscoveryExtension.cs**: der letzte Schritt in der Implementierung des Suchdiensts wird die Verbindung dieser Implementierung des benutzerdefinierten Suchdiensts mit den Diensthost. Die hier verwendete Hilfsklasse ist die `CustomDiscoveryExtension`-Klasse. Mit dieser Klasse wird die <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension>-Klasse erweitert. Der Benutzer muss die <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A>-Methode überschreiben. In diesem Fall gibt die Methode eine Instanz des benutzerdefinierten Ermittlungsdiensts zurück, der zuvor erstellt wurde. `PublishedEndpoints` ist eine <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, die alle dem <xref:System.ServiceModel.ServiceHost> hinzugefügten Anwendungsendpunkte enthält. Der benutzerdefinierte Suchdienst füllt damit seine interne Liste auf. Ein Benutzer kann auch weitere Endpunktmetadaten hinzufügen.  
  
 Öffnen Sie als letzten Schritt die Datei Program.cs. Beachten Sie, dass sowohl <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> als auch `CustomDiscoveryExtension` dem Host hinzugefügt werden. Sobald dies erfolgt ist und der Host über einen Endpunkt verfügt, über den Suchmeldungen empfangen werden können, kann der benutzerdefinierte Suchdienst von der Anwendung verwendet werden.  
  
 Beachten Sie, dass der Client den Dienst ermitteln kann, ohne seine Adresse zu kennen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Projektmappe, die das Projekt enthält.  
  
2.  Erstellen Sie das Projekt.  
  
3.  Führen Sie die Dienstanwendung aus.  
  
4.  Führen Sie die Clientanwendung aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\CustomFindCriteria`
