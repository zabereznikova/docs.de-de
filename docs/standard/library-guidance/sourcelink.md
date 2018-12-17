---
title: SourceLink und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Verwenden von SourceLink zur Verbesserung des Debuggens für .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128926"
---
# <a name="sourcelink"></a>SourceLink

SourceLink ist eine Technologie, mit der Entwickler Quellcode aus .NET-Assemblys über NuGet debuggen können. SourceLink wird beim Erstellen des NuGet-Pakets ausgeführt und bettet Metadaten der Quellcodeverwaltung in Assemblys und das Paket ein. Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können den Quellcode schrittweise ausführen. SourceLink bietet Metadaten zur Quellcodeverwaltung, um das Debuggen zu optimieren.

## <a name="sourcelink-demo"></a>SourceLink-Demo

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Verwenden von SourceLink

Anweisungen zum Verwenden von SourceLink finden Sie im GitHub-Repository [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Sie können mit dem [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) bestätigen, dass die SourceLink-Metadaten erfolgreich in das Paket eingebettet wurden. Überprüfen Sie, ob die `Repository`-Metadaten über einen Kommentarbezeichner verfügen, und ob sich PDB-Dateien in der jeweiligen DLL-Zieldatei befinden.

![SourceLink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink im NuGet-Paket-Explorer")

**✔️ Fügen** Sie mit SourceLink ggf. Metadaten der Quellcodeverwaltung Ihren Assemblys und NuGet-Paketen hinzu.

> [!TIP]
> Sie können für Entwickler den Debugvorgang weiter verbessern, indem Sie Ihren Typen Debuggerattribute hinzufügen.
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> kann anpassen, wie eine Klasse oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> weist den Debugger an, schrittweise durch den Code zu laufen, anstatt ihn schrittweise auszuführen.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> bestimmt, ob und wie ein Member in Debuggervariablenfenstern angezeigt wird.

**✔️ Betten** Sie Symboldateien (`*.pdb`) in das NuGet-Paket ein.

> Normalerweise werden Symboldateien in einem [Symbolpaket](./nuget.md#symbol-packages) veröffentlicht. Derzeit unterstützt der öffentliche Haupthost für Symbole nicht die portierbaren Symboldateien (`*.pdb`), die von SDK-Projekten erstellt wurden. Das bedeutet, Symbolpakete sind nicht nützlich.

>[!div class="step-by-step"]
>[Zurück](dependencies.md)
>[Weiter](publish-nuget-package.md)