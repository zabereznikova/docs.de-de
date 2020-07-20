---
title: 'Migrationshandbuch zu .NET Framework 4.8, 4.7, 4.6 und 4.5 '
description: Ein Leitfaden für die Migration zu neueren .NET Framework-Versionen mit Ressourcen für neue Features und Anwendungskompatibilität.
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: a5b632824efacdb5e99228727b8751dc7f17d363
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86443415"
---
# <a name="migrate-to-net-framework-48-47-46-and-45"></a>Migration zu .NET Framework 4.8, 4.7, 4.6 und 4.5

Wenn Sie Ihre App mit einer früheren Version des .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und die Nebenversionen (4.5.1 und 4.5.2), .NET Framework 4.6 und die Nebenversionen (4.6.1 und 4.6.2), .NET Framework 4.7 und die Nebenversionen (4.7.1 und 4.7.2) oder .NET Framework 4.8 ausführen. Öffnen Sie Ihr Projekt in Visual Studio. Wenn das Projekt in einer früheren Version von Visual Studio erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet. Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2019 – Zielplattformen und Kompatibilität](/visualstudio/releases/2019/compatibility).

 Einige Änderungen im .NET Framework erfordern jedoch Änderungen am Code. So möchten Sie möglicherweise die neuen Features von .NET Framework 4.5 und Nebenversionen, von .NET Framework 4.6 und Nebenversionen, von .NET Framework 4.7 und Nebenversionen oder .NET Framework 4.8 nutzen. Solche Änderungen an der App für eine neue Version von .NET Framework werden in der Regel als *Migration* bezeichnet. Wenn Ihre App nicht migriert werden muss, können Sie sie in .NET Framework 4.5 oder einer späteren Version ausführen, ohne sie neu zu kompilieren.

## <a name="migration-resources"></a>Migrationsressourcen

Lesen Sie die folgenden Dokumente, bevor Sie die App von früheren Versionen des .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 oder 4.8 migrieren:

- Lesen Sie [Versionen und Abhängigkeiten](versions-and-dependencies.md), damit Sie die CLR-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.

- Unter [Anwendungskompatibilität](application-compatibility.md) erhalten Sie Informationen zu Laufzeit- und Neuausrichtungsänderungen, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.

- Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.

- Unter [Neuigkeiten](../whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.

## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
- [Migrieren von .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Versionskompatibilität](version-compatibility.md)
- [Versionen und Abhängigkeiten](versions-and-dependencies.md)
- [How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Neuigkeiten](../whats-new/index.md)
- [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md)
- [Offizielle .NET Framework-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [.NET Framework 4 migration issues (Migrationsprobleme in .NET Framework 4)](net-framework-4-migration-issues.md)
