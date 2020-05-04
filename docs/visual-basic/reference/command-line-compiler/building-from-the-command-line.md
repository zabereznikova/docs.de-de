---
title: Erstellen von der Befehlszeile aus
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344792"
---
# <a name="building-from-the-command-line-visual-basic"></a>Erstellen von der Befehlszeile aus (Visual Basic)

Ein Visual Basic-Projekt besteht aus einer oder mehreren separaten Quelldateien. Während des Prozesses, der als Kompilierung bezeichnet wird, werden diese Dateien in einem Paket zusammengefasst: einer einzelnen ausführbaren Datei, die als Anwendung ausgeführt werden kann.

Visual Basic bietet mit dem Befehlszeilencompiler eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Der Befehlszeilencompiler ist für Situationen konzipiert, in denen Sie nicht alle Features der IDE benötigen – beispielsweise wenn Sie Programme für Computer mit eingeschränktem Systemarbeitsspeicher oder -speicher verwenden oder schreiben.

Wenn Sie Quelldateien in der Visual Studio-IDE kompilieren möchten, klicken Sie im Menü **Erstellen** auf **Kompilieren**.

> [!TIP]
> Wenn Sie Projektdateien mit der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten Befehl **vbc** und dessen Parameter im Ausgabefenster anzeigen. Navigieren Sie hierzu zu [Optionen > Projekte und Projektmappen > Kompilieren und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie die **Ausführlichkeit der MSBuild-Projektbuildausgabe** auf **Normal** oder höher fest. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).

Sie können Projektdateien (.vbproj) mithilfe von MSBuild in einer Eingabeaufforderung kompilieren. Weitere Informationen finden Sie unter [Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>In diesem Abschnitt

[How to: Aufrufen des Befehlszeilencompilers](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) \
Beschreibt, wie der Befehlszeilencompiler in der MS-DOS-Eingabeaufforderung oder über ein bestimmtes Unterverzeichnis aufgerufen wird.

[Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) \
Enthält eine Liste mit Beispielbefehlszeilen, die Sie nach Belieben anpassen können.

## <a name="related-sections"></a>Verwandte Abschnitte

[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) \
Enthält Listen mit Compileroptionen, die alphabetisch oder nach Zweck angeordnet sind.

[Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) \
Beschreibt, wie bestimmte Codeabschnitte kompiliert werden.

[Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \
Beschreibt, wie Sie die in verschiedenen Builds enthaltenen Elemente organisieren, Projekteigenschaften auswählen und sicherstellen, dass Projekte in der richtigen Reihenfolge erstellt werden.
