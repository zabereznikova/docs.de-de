---
title: Beispiele für Kompilierungsbefehlszeilen
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 496627d3b77b0382ae7d15c8225a6fbd41f1db73
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403121"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiele für Kompilierungsbefehlszeilen (Visual Basic)

Alternativ zum Kompilieren von Visual Basic-Programmen in Visual Studio können Sie diese über die Befehlszeile kompilieren, um ausführbare Dateien (.exe) oder DLL-Dateien (.dll) zu erstellen.

Der Visual Basic-Befehlszeilencompiler unterstützt sämtliche Optionen, die Eingabe- und Ausgabedateien, Assemblys sowie Debug- und Präprozessoroptionen steuern. Jede Option ist in zwei austauschbaren Formaten verfügbar: `-option` und `/option`. In dieser Dokumentation wird nur das `-option`-Format dargestellt.

In der folgenden Tabelle sind einige Beispielbefehlszeilen aufgelistet, die Sie anpassen können.

|Beschreibung|Verwendung|
|--------|---------|
|Kompiliert „File.vb“ und erstellt „File.exe“|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Kompiliert „File.vb“ und erstellt „File.dll“|`vbc -target:library File.vb`|
|Kompiliert „File.vb“ und erstellt „My.exe“|`vbc -out:My.exe File.vb`|
|Kompiliert „File.vb“ und erstellt eine Bibliothek und eine Verweisassembly namens „File.dll“|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen dem definierten `DEBUG`-Symbol und erstellt „File2.exe“|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis und erstellt eine Debugversion von „File2.dll“, ohne das Logo oder Warnungen anzuzeigen|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Kompiliert alle C#-Dateien im aktuellen Verzeichnis zu „Something.dll“|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Wenn Sie ein Projekt mit der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten Befehl **vbc** und dessen Compileroptionen im Ausgabefenster anzeigen. Navigieren Sie hierzu zu [Optionen > Projekte und Projektmappen > Kompilieren und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie die **Ausführlichkeit der MSBuild-Projektbuildausgabe** auf **Normal** oder höher fest.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
