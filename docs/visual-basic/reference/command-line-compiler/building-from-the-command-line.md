---
title: Erstellen von der Befehlszeile aus (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers, invoking from command line
- command-line builds
- compiling source code
- command-line compilers, Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 49f84c221e18457ab46534ca46da7c4764a8ee40
ms.lasthandoff: 03/13/2017

---
# <a name="building-from-the-command-line-visual-basic"></a>Erstellen von der Befehlszeile aus (Visual Basic)
Ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekt besteht aus einem oder mehreren separaten Quelldateien. Bei der Kompilierung genannt, werden diese Dateien in einem Paket zusammengefasst – einer einzelnen ausführbaren Datei, die als eine Anwendung ausgeführt werden kann.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Stellt einen Befehlszeilencompiler als Alternative zum Kompilieren von Programmen in der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] integrierten Entwicklungsumgebung (IDE). Der Befehlszeilencompiler eignet sich für Situationen, in dem Sie den vollständigen Satz von Funktionen in der IDE nicht benötigen, z. B. Wenn Sie mithilfe von oder für Computer mit begrenztem Arbeitsspeicher oder ein Speicherplatz schreiben.  
  
 Beim Kompilieren von der Befehlszeile aus müssen Sie explizit verweisen, auf die Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Laufzeitbibliothek über die `/reference` -Compileroption.  
  
 Zum Kompilieren von Quelldateien in der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] IDE, wählen Sie die **erstellen** Befehl die **erstellen** im Menü.  
  
> [!TIP]
>  Wenn Sie Dateien mithilfe von Visual Studio-IDE erstellen, können Sie anzeigen, Informationen zum zugehörigen **Vbc** Befehl und Schaltern im Ausgabefenster angezeigt. Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder eine höhere Stufe der Ausführlichkeit. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Sie können Projektdateien (.vbproj) in einer Befehlszeile kompilieren, mithilfe von MSBuild. Weitere Informationen finden Sie unter [-Befehlszeilenreferenz](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Aufrufen des Befehlszeilencompilers](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Beschreibt das Aufrufen des Befehlszeilencompilers auf MS-DOS oder von einem bestimmten Unterverzeichnis.  
  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Enthält eine Liste mit Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 Enthält eine Liste der Compileroptionen alphabetisch oder nach ihrem Zweck geordnet sind.  
  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Beschreibt, wie bestimmte Codeabschnitte kompiliert.  
  
 [Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio](https://docs.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Beschreibt das Organisieren, was in verschiedenen Builds eingeschlossen, Projekteigenschaften auswählen und sicherstellen, dass Projekte in der richtigen Reihenfolge erstellen.
