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
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350855"
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

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
