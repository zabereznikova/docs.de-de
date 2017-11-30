---
title: "Kompatibilität von .NET Framework-Versionen"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 166d61339d2b74f378b50ade4b78fd41e9692f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
 Wegen dieser Einschränkung sind Kompatibilitätsgarantien für Komponenten besonders wichtig. Ab .NET Framework 4 können Sie den Grad der Kompatibilität einer Komponente mit mehreren Versionen angeben. Dazu wenden Sie das <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType>-Attribut auf diese Komponente an. Tools können mithilfe dieses Attributs potenzielle Verletzungen der Kompatibilitätsgarantie in zukünftigen Versionen einer Komponente erkennen.  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>Abwärtskompatibilität und .NET Framework 4.5  
 Die .NET Framework 4.5 und höher sind abwärtskompatibel mit apps, die mit früheren Versionen von .NET Framework erstellt wurden. Das heißt, funktioniert apps und Komponenten, die mit früheren Versionen ohne Änderung auf die .NET Framework 4.5 und höher. Allerdings werden standardmäßig, ausgeführt apps auf die Version der common Language Runtime für die sie entwickelt wurden, daher Sie zum Angeben einer Konfigurationsdatei, damit Ihre Anwendung auf dem .NET Framework 4.5 oder höher ausgeführt müssen. Weitere Informationen finden Sie im Abschnitt [Versionskompatibilität für Apps](#Apps) weiter oben in diesem Artikel.  
  
 In der Praxis kann diese Kompatibilität von scheinbar belanglosen Änderungen in .NET Framework und von Änderungen in den Programmierverfahren aufgehoben werden. Leistungsverbesserungen an .NET Framework 4.5 können z. B. eine Racebedingung mit sich bringen, die unter früheren Versionen nicht aufgetreten ist. Auf ähnliche Weise sind das Verwenden eines hartcodierten Pfads zu .NET Framework-Assemblys, das Ausführen eines Gleichheitsvergleich mit einer bestimmten Version von .NET Framework und das Abrufen des Werts eines privaten Felds mithilfe einer Reflektion keine abwärtskompatiblen Maßnahmen. Außerdem schließt jede Version von .NET Framework Fehlerkorrekturen und sicherheitsbezogene Änderungen ein, die sich auf die Kompatibilität von einigen Apps und Komponenten auswirken können.  
  
 Wenn Ihre app oder Komponente nicht ordnungsgemäß funktioniert, wie erwartet auf .NET Framework 4.5 (einschließlich punktreleases, die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 oder 4.7.1, verwenden Sie die folgenden Prüflisten:  
  
-  Wenn Ihre app entwickelt wurde, um auf eine beliebige Version von .NET Framework beginnend mit .NET Framework 4.0 ausgeführt wird, finden Sie unter [Anwendungskompatibilität in .NET Framework](application-compatibility.md) zum Generieren von Listen von Änderungen zwischen der Zielversion von .NET Framework und die Version auf der die app ausgeführt wird.  

- Wenn Sie eine .NET Framework 3.5-app haben, finden Sie auch unter [.NET Framework 4-Migrationsprobleme](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md).

- Wenn Sie eine .NET Framework 2.0-app haben, finden Sie auch unter [Änderungen in .NET Framework 3.5 SP1](http://go.microsoft.com/fwlink/?LinkId=186989).

- Wenn Sie eine .NET Framework 1.1-app haben, finden Sie auch unter [Änderungen in .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125263).  
  
-   Wenn Sie vorhandenen Quellcode zum Ausführen von auf .NET Framework 4.5 oder dessen Punkt Versionen neu kompilieren müssen, oder entwickeln Sie eine neue Version einer app oder Komponente, die als Ziel verwendet die [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder dessen Punktversionen aus einer vorhandenen Quelle Code Basisentität Kontrollkästchen [ Was ist, dass veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md) veraltete Typen und Member, und weisen Sie die beschriebene problemumgehung. (Bereits kompilierter Code wird weiterhin mit Typen und Membern ausgeführt, die als veraltet markiert wurden.)  
  
-   Wenn Sie feststellen, dass eine Änderung in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] das ordnungsgemäße Funktionieren der App verhindert hat, überprüfen Sie im [Schema für Laufzeiteinstellungen](../../../docs/framework/configure-apps/file-schema/runtime/index.md), ob Sie eine Laufzeiteinstellung in der App-Konfigurationsdatei verwenden können, um das vorherige Verhalten wiederherzustellen.  
  
-   Wenn ein Problem auftritt, das nicht dokumentiert ist, melden Sie den [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815)-Fehler und wenden Sie sich mit der Fehlernummer an [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com).  
  
## <a name="compatibility-and-side-by-side-execution"></a>Kompatibilität und parallele Ausführung  
 Wenn Sie keine geeignete Problemumgehung für das Problem finden können, beachten Sie, dass .NET Framework 4.5 (oder eine seiner Punktreleases) parallel mit den Versionen 1.1, 2.0 und 3.5 ausgeführt werden kann, und ein direktes Update ist, das Version 4 ersetzt. Sie können für Apps, die auf die Versionen 1.1, 2.0 und 3.5 ausgerichtet sind, die entsprechende Version von .NET Framework auf dem Zielcomputer installieren, um die App in der optimalen Umgebung auszuführen. Weitere Informationen über die parallele Ausführung finden Sie unter [Parallele Ausführung](../../../docs/framework/deployment/side-by-side-execution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Neuigkeiten](../../../docs/framework/whats-new/index.md)  
 [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)  
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Microsoft .NET Framework Support Lifecycle-Richtlinien](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [Migrationsprobleme in .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)
