---
title: "Migrationshandbuch zu .NET Framework 4.6 und 4.5 | Microsoft-Dokumentation"
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
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 9004e102dac346e7d7d627f5adc573a18a53952e
ms.lasthandoff: 04/08/2017

---
# <a name="migration-guide-to-the-net-framework-46-and-45"></a>Migrationshandbuch zu .NET Framework 4.6 und 4.5 
Wenn Sie Ihre Anwendung mit einer früheren Version von .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und dessen Punktreleases (4.5.1 und 4.5.2), .NET Framework 4.6 und dessen Punktreleases (4.6.1 und 4.6.2) oder .NET Framework 4.7 durchführen. Öffnen Sie Ihr Projekt in Visual Studio. Wenn das Projekt in einer früheren Version erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet. Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](https://docs.microsoft.com/en-us/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2017 – Zielplattformen und Kompatibilität](https://www.visualstudio.com/en-us/productinfo/vs2017-compatibility-vs).  
  
 Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code. So möchten Sie möglicherweise die neuen Funktionen von .NET Framework 4.5 und dessen Punktreleases, von .NET Framework 4.6 und dessen Punktreleases sowie von .NET Framework 4.7 nutzen. Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet. Wenn Ihre App nicht migriert werden muss, können Sie diese in .NET Framework 4.5 oder neueren Versionen ohne Neukompilieren ausführen.  
  
## <a name="migration-resources"></a>Migrationsressourcen  
 Überprüfen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2 oder 4.7 migrieren:  
  
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
 [Microsoft .NET Framework Support Lifecycle-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=196607)
