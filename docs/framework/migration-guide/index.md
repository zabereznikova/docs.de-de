---
title: 'Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5 '
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c1f9ffd1df3861c2e9b000faccae381b04295dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a>Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5 
Wenn Sie Ihre App mit einer früheren Version von .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und die Nebenversionen (4.5.1 und 4.5.2), .NET Framework 4.6 und die Nebenversionen (4.6.1 und 4.6.2) oder .NET Framework 4.7 und die Nebenversion (4.7.1) ausführen. Öffnen Sie Ihr Projekt in Visual Studio. Wenn das Projekt in einer früheren Version von Visual Studio erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet. Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2017 – Zielplattformen und Kompatibilität](https://www.visualstudio.com/en-us/productinfo/vs2017-compatibility-vs).  
  
 Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code. So möchten Sie möglicherweise die neuen Funktionen von .NET Framework 4.5 und den Nebenversionen, von .NET Framework 4.6 und den Nebenversionen sowie von .NET Framework 4.7 und der Nebenversion (4.7.1) nutzen. Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet. Wenn Ihre Anwendung nicht migriert werden muss, können Sie sie in .NET Framework 4.5 oder einer späteren Version ausführen, ohne sie neu zu kompilieren.  
  
## <a name="migration-resources"></a>Migrationsressourcen  
 Lesen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 oder 4.7.1 migrieren:  
  
-   Lesen Sie [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md), damit Sie die CLR-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.  
  
-   Lesen Sie [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md), um Informationen zu Laufzeit- und Neuausrichtungsänderungen zu erhalten, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.  
  
-   Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.  
  
-   Unter [Neuigkeiten](../../../docs/framework/whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [Versionskompatibilität](../../../docs/framework/migration-guide/version-compatibility.md)  
 [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [Gewusst wie: Konfigurieren einer App für die Unterstützung von .NET Framework 4 oder 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [Neuigkeiten](../../../docs/framework/whats-new/index.md)  
 [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)  
 [Versions- und Assemblyinformationen zu .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701)  
 [Microsoft .NET Framework Support Lifecycle-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=196607) [Migrationsprobleme in .NET Framework 4](net-framework-4-migration-issues.md)
