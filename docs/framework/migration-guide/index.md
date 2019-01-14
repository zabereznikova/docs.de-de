---
title: 'Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5 '
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9c537aa8fff5fdf823effeae42382ee499efaf4
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221501"
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a>Migrationshandbuch zu .NET Framework 4.7, 4.6 und 4.5

Wenn Sie Ihre App mit einer früheren Version von .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und die Nebenversionen (4.5.1 und 4.5.2), .NET Framework 4.6 und die Nebenversionen (4.6.1 und 4.6.2) oder .NET Framework 4.7 und seine Nebenversionen (4.7.1 und 4.7.2) ausführen. Öffnen Sie Ihr Projekt in Visual Studio. Wenn das Projekt in einer früheren Version von Visual Studio erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet. Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2017 – Zielplattformen und Kompatibilität](/visualstudio/productinfo/vs2017-compatibility-vs).

 Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code. So möchten Sie möglicherweise die neuen Funktionen von .NET Framework 4.5 und Nebenversionen, von .NET Framework 4.6 und Nebenversionen sowie von .NET Framework 4.7 und Nebenversionen nutzen. Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet. Wenn Ihre Anwendung nicht migriert werden muss, können Sie sie in .NET Framework 4.5 oder einer späteren Version ausführen, ohne sie neu zu kompilieren.

## <a name="migration-resources"></a>Migrationsressourcen

Lesen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1 oder 4.7.2 migrieren:

- Lesen Sie [Versionen und Abhängigkeiten](versions-and-dependencies.md), damit Sie die CLR-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.

- Lesen Sie [Anwendungskompatibilität](application-compatibility.md), um Informationen zu Laufzeit- und Neuausrichtungsänderungen zu erhalten, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.

- Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.

- Unter [Neuigkeiten](../whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.

## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
- [Migrieren von .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Versionskompatibilität](version-compatibility.md)
- [Versionen und Abhängigkeiten](versions-and-dependencies.md)
- [Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Neuigkeiten](../whats-new/index.md)
- [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md)
- [Versions- und Assemblyinformationen zu .NET Framework](https://go.microsoft.com/fwlink/?LinkId=201701)
- [Microsoft .NET Framework Support Lifecycle-Richtlinien](https://go.microsoft.com/fwlink/?LinkId=196607)
- [.NET Framework 4 migration issues (Migrationsprobleme in .NET Framework 4)](net-framework-4-migration-issues.md)