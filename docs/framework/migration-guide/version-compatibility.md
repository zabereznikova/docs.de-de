---
title: "Kompatibilität von .NET Framework-Versionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
caps.latest.revision: 35
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 09f682d9c3a1cf5d42bba878676d84b9328a1a81
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="version-compatibility-in-the-net-framework"></a>Kompatibilität von .NET Framework-Versionen
Abwärtskompatibilität bedeutet, dass eine für eine bestimmte Version einer Plattform entwickelte App in höheren Versionen dieser Plattform ausgeführt werden kann. Bei .NET Framework wird versucht, die Abwärtskompatibilität zu maximieren: Für eine Version von .NET Framework geschriebener Quellcode wird auf höheren Versionen von .NET Framework kompiliert, und Binärdateien, die auf einer Version von .NET Framework ausgeführt werden, verhalten sich auch auf höheren Versionen von .NET Framework gleich.  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a>Versionskompatibilität für Apps  
 Standardmäßig wird eine App in der Version von .NET Framework ausgeführt, für die sie erstellt wurde. Wenn diese Version nicht vorhanden ist und die App-Konfigurationsdatei keine unterstützten Versionen definiert, tritt möglicherweise ein .NET Framework-Initialisierungsfehler auf. In diesem Fall schlägt der Versuch fehl, die App auszuführen.  
  
 Fügen Sie der Konfigurationsdatei der App ein oder mehrere [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)-Elemente hinzu, um die Versionen zu definieren, in denen die App ausgeführt werden kann. Jedes `<supportedRuntime>`-Element führt eine unterstützte Version der Laufzeit auf. Dabei gibt das erste Element die bevorzugte Version der Laufzeit an und das letzte die am wenigsten bevorzugte Version.  
  
```xml  
  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
  
```  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Konfigurieren einer App für die Unterstützung von .NET Framework 4 oder 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).  
  
## <a name="version-compatibility-for-components"></a>Versionskompatibilität für Komponenten  
 Eine App kann die Version von .NET Framework steuern, in der sie ausgeführt wird. Eine Komponente kann das jedoch nicht. Komponenten und Klassenbibliotheken werden im Kontext einer bestimmten App geladen und daher automatisch in der Version von .NET Framework ausgeführt, in der die App ausgeführt wird.  
  
 Wegen dieser Einschränkung sind Kompatibilitätsgarantien für Komponenten besonders wichtig. Ab .NET Framework 4 können Sie den Grad der Kompatibilität einer Komponente mit mehreren Versionen angeben. Dazu wenden Sie das <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=fullName>-Attribut auf diese Komponente an. Tools können mithilfe dieses Attributs potenzielle Verletzungen der Kompatibilitätsgarantie in zukünftigen Versionen einer Komponente erkennen.  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>Abwärtskompatibilität und .NET Framework 4.5  
 .NET Framework 4.5 und die zugehörigen Punktreleases (4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2 und 4.7) sind mit Apps abwärtskompatibel, die mit früheren Versionen von .NET Framework erstellt wurden. Das heißt, Apps und Komponenten, die mit früheren Versionen von .NET Framework erstellt wurden, funktionieren ohne weitere Änderung auch in .NET Framework 4.5. Allerdings werden Apps standardmäßig in der Version der Common Language Runtime ausgeführt, für die sie entwickelt wurden. Daher müssen Sie eine Konfigurationsdatei bereitstellen, damit die App in .NET Framework 4.5 ausgeführt werden kann. Weitere Informationen finden Sie im Abschnitt [Versionskompatibilität für Apps](#Apps) weiter oben in diesem Artikel.  
  
 In der Praxis kann diese Kompatibilität von scheinbar belanglosen Änderungen in .NET Framework und von Änderungen in den Programmierverfahren aufgehoben werden. Leistungsverbesserungen an .NET Framework 4.5 können z. B. eine Racebedingung mit sich bringen, die unter früheren Versionen nicht aufgetreten ist. Auf ähnliche Weise sind das Verwenden eines hartcodierten Pfads zu .NET Framework-Assemblys, das Ausführen eines Gleichheitsvergleich mit einer bestimmten Version von .NET Framework und das Abrufen des Werts eines privaten Felds mithilfe einer Reflektion keine abwärtskompatiblen Maßnahmen. Außerdem schließt jede Version von .NET Framework Fehlerkorrekturen und sicherheitsbezogene Änderungen ein, die sich auf die Kompatibilität von einigen Apps und Komponenten auswirken können.  
  
 Wenn Ihre App oder Komponente nicht wie erwartet in .NET Framework 4.5 (einschließlich der Punktreleases [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2 oder 4.7) funktioniert, verwenden Sie die folgende Prüfliste:  
  
-   Überprüfen Sie in diesen Themen, ob es Änderungen gibt, die sich auf Ihre App auswirken könnten, und umgehen Sie das jeweilige Problem wie beschrieben:  
  
    -   [Migrationsprobleme in .NET Framework 4](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
  
    -   [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)  
  
    -   [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)  
  
    -   [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)  
  
    -   [Anwendungskompatibilität in 4.6](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6.md)  
  
    -   [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
    -   [Anwendungskompatibilität in 4.6.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)  

    - [Anwendungskompatibilität in 4.7](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
       
-   Wenn Sie eine .NET Framework 1.1-App haben, sollten Sie auch diese Themen lesen:  
  
    -   [Änderungen in .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125263)  
  
    -   [Änderungen in .NET Framework 3.5 SP1](http://go.microsoft.com/fwlink/?LinkId=186989)  
  
-   Wenn Sie vorhandenen Quellcode neu kompilieren, sodass er in .NET Framework 4.5 oder seinen Punktreleases ausgeführt werden kann, oder wenn Sie eine neue Version einer App oder einer Komponente entwickeln, die basierend auf vorhandenem Quellcode auf [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ausgerichtet ist, überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md) auf veraltete Typen und Member, und wenden Sie die beschriebene Problemumgehung an. (Bereits kompilierter Code wird weiterhin mit Typen und Membern ausgeführt, die als veraltet markiert wurden.)  
  
-   Wenn Sie feststellen, dass eine Änderung in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] das ordnungsgemäße Funktionieren der App verhindert hat, überprüfen Sie im [Schema für Laufzeiteinstellungen](../../../docs/framework/configure-apps/file-schema/runtime/index.md), ob Sie eine Laufzeiteinstellung in der App-Konfigurationsdatei verwenden können, um das vorherige Verhalten wiederherzustellen.  
  
-   Wenn ein Problem auftritt, das nicht dokumentiert ist, melden Sie den [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815)-Fehler und wenden Sie sich mit der Fehlernummer an [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com).  
  
## <a name="compatibility-and-side-by-side-execution"></a>Kompatibilität und parallele Ausführung  
 Wenn Sie keine geeignete Problemumgehung für das Problem finden können, beachten Sie, dass .NET Framework 4.5 (oder eine seiner Punktreleases) parallel mit den Versionen 1.1, 2.0 und 3.5 ausgeführt werden kann, und ein direktes Update ist, das Version 4 ersetzt. Sie können für Apps, die auf die Versionen 1.1, 2.0 und 3.5 ausgerichtet sind, die entsprechende Version von .NET Framework auf dem Zielcomputer installieren, um die App in der optimalen Umgebung auszuführen. Weitere Informationen über die parallele Ausführung finden Sie unter [Parallele Ausführung](../../../docs/framework/deployment/side-by-side-execution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Neuigkeiten](../../../docs/framework/whats-new/index.md)   
 [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)   
 [Microsoft .NET Framework Support Lifecycle-Richtlinien](http://go.microsoft.com/fwlink/p/?LinkId=248212)   
 [Migrationsprobleme in .NET Framework 4](http://go.microsoft.com/fwlink/p/?LinkId=248212)
