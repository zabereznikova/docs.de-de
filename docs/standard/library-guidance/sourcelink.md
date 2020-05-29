---
title: SourceLink und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Verwenden von SourceLink zur Verbesserung des Debuggens für .NET-Bibliotheken.
ms.date: 01/15/2019
ms.openlocfilehash: 0261019087bce8e9d088a90c5e36bdd0b22f556b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212424"
---
# <a name="source-link"></a>SourceLink

SourceLink ist eine Technologie, mit der Entwickler Quellcode aus .NET-Assemblys über NuGet debuggen können. SourceLink wird beim Erstellen des NuGet-Pakets ausgeführt und bettet Metadaten der Quellcodeverwaltung in Assemblys und das Paket ein. Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können den Quellcode schrittweise ausführen. SourceLink bietet Metadaten zur Quellcodeverwaltung, um das Debuggen zu optimieren.

## <a name="source-link-demo"></a>SourceLink-Demo

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a>Verwenden von SourceLink

Anweisungen zum Verwenden von SourceLink finden Sie im GitHub-Repository [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Sie können mit dem [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) bestätigen, dass die SourceLink-Metadaten erfolgreich in das Paket eingebettet wurden. Überprüfen Sie, ob die `Repository`-Metadaten über eine Commit-ID verfügen, und ob sich PDB-Dateien in der jeweiligen DLL-Zieldatei befinden.

![Quellenlink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Quellenlink im NuGet-Paket-Explorer")

✔️ Erwägen Sie, Ihren Assemblys und NuGet-Paketen gegebenenfalls mithilfe von Source Link Metadaten der Quellcodeverwaltung hinzuzufügen.

> [!TIP]
> Sie können für Entwickler den Debugvorgang weiter verbessern, indem Sie Ihren Typen Debuggerattribute hinzufügen.
>
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> kann anpassen, wie eine Klasse oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> weist den Debugger an, schrittweise durch den Code zu laufen, anstatt ihn schrittweise auszuführen.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> bestimmt, ob und wie ein Member in Debuggervariablenfenstern angezeigt wird.

✔️ Erwägen Sie, Symboldateien zu veröffentlichen (`*.pdb`).

> Für das beste Debugergebnis sollte Ihre Bibliothek sowohl Symboldateien veröffentlichen als auch SourceLink verwenden. Weitere Informationen zu Symboldateien und Symbolpaketen finden Sie unter [Symbolpakete](./nuget.md#symbol-packages).

✔️ ERWÄGEN SIE, deterministische Builds zu aktivieren.

> Deterministische Builds ermöglichen die Überprüfung, ob die resultierende Binärdatei aus der angegebenen Quelle erstellt wurde, und die Nachverfolgbarkeit. Weitere Informationen zu deterministischen Builds und Anweisungen zu deren Aktivierung finden Sie unter [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds) (Deterministische Builds).

>[!div class="step-by-step"]
>[Zurück](dependencies.md)
>[Weiter](publish-nuget-package.md)
