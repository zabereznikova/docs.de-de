---
title: "Migrationshandbuch zu .NET Framework&#160;4.6 und 4.5  | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, Migrieren von Anwendungen zu"
  - "Migration, .NET Framework"
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Migrationshandbuch zu .NET Framework&#160;4.6 und 4.5 
Wenn Sie die App mithilfe einer früheren Version von .NET Framework erstellt haben, ist das Upgrade auf .NET Framework 4.5, 4.5.1 oder 4.6 in der Regel ganz einfach. Öffnen Sie Ihr Projekt in Visual Studio. Wenn das Projekt in einer früheren Version erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet. Weitere Informationen zum Upgraden eines Projekts in Visual Studio 2013 finden Sie unter [Gewusst wie: Upgraden von in früheren Versionen von Visual Studio erstellten Projekten](http://msdn.microsoft.com/library/vstudio/ms185327\(v=vs.100\).aspx) und [Portieren, Migrieren und Aktualisieren von Visual Studio\-Projekten](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md).  
  
 Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code. So möchten Sie möglicherweise die neuen Funktionen von .NET Framework 4.5, dessen Punktversionen oder von .NET Framework 4.6 nutzen. Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet. Wenn Ihre App nicht migriert werden muss, können Sie diese in .NET Framework 4.5 oder neueren Versionen ohne Neukompilieren ausführen.  
  
## Migrationsressourcen  
 Überprüfen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1 oder 4.5.2 migrieren:  
  
-   Lesen Sie [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md), damit Sie die CLR\-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.  
  
-   Lesen Sie [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md), um Informationen zu Laufzeit\- und Neuausrichtungsänderungen zu erhalten, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.  
  
-   Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.  
  
-   Unter [Neues](../../../docs/framework/whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.  
  
## Siehe auch  
 [Anwendungskompatibilität in 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Versionskompatibilität](../../../docs/framework/migration-guide/version-compatibility.md)   
 [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Gewusst wie: Konfigurieren einer Anwendung für die Unterstützung von .NET Framework 4 oder 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [Neues](../../../docs/framework/whats-new/index.md)   
 [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Versions\- und Assemblyinformationen zu .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701)   
 [Microsoft .NET Framework Support Lifecycle\-Richtlinien](http://go.microsoft.com/fwlink/?LinkId=196607)