---
title: Erstellen von der Befehlszeile aus (Visual Basic)
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
ms.openlocfilehash: 391e16da86aa741a1b78f35d9afd95688f33c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654134"
---
# <a name="building-from-the-command-line-visual-basic"></a>Erstellen von der Befehlszeile aus (Visual Basic)
Ein Visual Basic-Projekt besteht aus einem oder mehreren separaten Quelldateien. Während des Prozesses, der als Kompilierung bezeichnet wird, werden diese Dateien in einem Paket zusammengefasst – eine einzelne ausführbare Datei, die als eine Anwendung ausgeführt werden kann.  
  
 Visual Basic bietet einen Befehlszeilencompiler als Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Der Befehlszeilencompiler eignet sich für Situationen, in dem Sie den vollständigen Satz von Funktionen der IDE nicht benötigen – z. B. Wenn Sie mithilfe von oder Schreiben von für Computer mit begrenztem Arbeitsspeicher oder Speicherplatz.  
  
  Um Quelldateien in der Visual Studio-IDE zu kompilieren, wählen Sie die **erstellen** Befehl die **erstellen** Menü.  
  
> [!TIP]
>  Wenn Sie über die Visual Studio-IDE Projektdateien erstellen, können Sie Informationen zum zugehörigen anzeigen **Vbc** Befehl und seine Switches im Ausgabefenster angezeigt. Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder ein höheres Maß an Ausführlichkeit. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Sie können die Projektdateien (.vbproj) an einer Eingabeaufforderung kompilieren, mithilfe von MSBuild. Weitere Informationen finden Sie unter [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Aufrufen des Befehlszeilencompilers](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Beschreibt, wie zum Aufrufen des Befehlszeilencompilers an der MS-DOS-Eingabeaufforderung oder von einem bestimmten Unterverzeichnis.  
  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Enthält eine Liste der Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 Enthält Listen von Compileroptionen alphabetisch oder nach ihrem Zweck organisiert.  
  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Beschreibt, wie bestimmte Codeabschnitte zu kompilieren.  
  
 [Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Beschreibt, wie zum Organisieren, was in verschiedene Builds enthalten, wählen Sie die Projekteigenschaften und stellen Sie sicher, dass Projekte in der richtigen Reihenfolge erstellen.
