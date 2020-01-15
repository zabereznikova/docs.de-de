---
title: Portieren von .NET Framework zu .NET Core
description: Verstehen Sie den Portiervorgang und entdecken Sie Tools, die Ihnen beim Portieren eines .NET Framework-Projekts zu .NET Core behilflich sein können.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937316"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Übersicht über das Portieren von .NET Framework zu .NET Core

Möglicherweise verfügen Sie über Code, der zurzeit im .NET Framework ausgeführt wird und den Sie zu .NET Core portieren möchten. Dieser Artikel enthält:

* Übersicht über den Portiervorgang.
* Eine Liste der Tools, die beim Portieren Ihres Codes zu .NET Core nützlich sein können.

## <a name="overview-of-the-porting-process"></a>Übersicht über den Portiervorgang

Die folgende Vorgehensweise wird empfohlen, um Ihr Projekt zu .NET Core zu portieren:

1. Legen Sie für alle zu portierenden Projekte .NET Framework 4.7.2 oder höher als neues Ziel fest.

   Durch diesen Schritt wird sichergestellt, dass Sie API-Alternativen für bestimmte .NET Framework-Ziele verwenden können, falls .NET Core eine bestimmte API nicht unterstützt.

2. Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um Ihre Assemblys zu analysieren und zu ermitteln, ob sie zu .NET Core portiert werden können.

   Das API Portability Analyzer-Tool analysiert Ihre kompilierten Assemblys und generiert einen Bericht. Dieser Bericht zeigt eine allgemeine Übersicht über die Portierbarkeit und eine Aufschlüsselung nach allen von Ihnen verwendeten APIs, die in .NET Core nicht verfügbar sind.

3. Installieren Sie das [.NET API-Analysetool](../../standard/analyzers/api-analyzer.md) in Ihren Projekten, um APIs zu identifizieren, die eine <xref:System.PlatformNotSupportedException> für einige Plattformen auslösen, und um weitere potenzielle Kompatibilitätsprobleme zu ermitteln.

   Dieses Tool ähnelt Portability Analyzer, analysiert jedoch nicht, ob Code in .NET Core kompiliert werden kann, sondern ob Sie eine API auf eine Weise verwenden, die zur Laufzeit eine <xref:System.PlatformNotSupportedException> auslöst. Wenn Sie von .NET Framework 4.7.2 oder höher wechseln, ist dies zwar nicht häufig der Fall, aber eine Überprüfung ist dennoch eine gute Idee. Weitere Informationen zu APIs, die Ausnahmen in .NET Core auslösen, finden Sie unter [APIs, die grundsätzlich Ausnahmen in .NET Core auslösen](../compatibility/unsupported-apis.md).

4. Konvertieren Sie alle `packages.config`-Abhängigkeiten mit dem [Konvertierungstool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference) in das [PackageReference](/nuget/consume-packages/package-references-in-project-files)-Format.

   Zu diesem Schritt gehört auch die Konvertierung von Abhängigkeiten aus dem `packages.config`-Legacyformat. `packages.config` funktioniert in .NET Core nicht, daher ist diese Konvertierung notwendig, wenn Paketabhängigkeiten vorhanden sind.

5. Erstellen Sie neue Projekte für .NET Core, und kopieren Sie die Quelldateien, oder versuchen Sie, Ihre vorhandene Projektdatei mithilfe eines Tools zu konvertieren.

   .NET Core verwendet ein einfacheres (und anderes) [Projektdateiformat](../tools/csproj.md) als .NET Framework. Sie müssen Ihre Projektdateien in dieses Format konvertieren, um sie weiter nutzen zu können.

6. Portieren Sie Ihren Testcode.

   Die Portierung auf .NET Core stellt eine erhebliche Änderung Ihrer Codebase dar, deshalb wird dringend empfohlen, Ihre Testprojekte zu portieren. Auf diese Weise können Sie Tests ausführen, wenn Sie Ihren Code portieren. MSTest, xUnit und NUnit funktionieren in .NET Core.

Darüber hinaus können Sie versuchen, kleinere Lösungen oder einzelne Projekte mit dem Tool [dotnet try-convert](https://github.com/dotnet/try-convert) in einem einzigen Vorgang in das .NET Core-Projektdateiformat zu portieren. Es kann nicht garantiert werden, dass `dotnet try-convert` für all Ihre Projekte funktioniert, und es kann zu leichten Abweichungen bei Verhalten kommen, das Sie unbedingt benötigen. Verwenden Sie das Tool als _Ausgangspunkt_, um grundlegende Elemente zu automatisieren, die sich für eine Automatisierung eignen. Es ist keine garantierte Lösung zum Migrieren eines Projekts.

## <a name="next-steps"></a>Nächste Schritte

>[!div class="nextstepaction"]
>[Analysieren von Abhängigkeiten](third-party-deps.md)
