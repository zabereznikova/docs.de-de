---
title: "Beispiele für Kompilierungsbefehlszeilen (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
Als Alternative zum Kompilieren von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] innerhalb von Programmen [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], können Sie kompilieren über die Befehlszeile, um ausführbare Dateien (.exe) oder Dynamic Link Library (DLL)-Dateien zu erzeugen.  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen, die Eingabe-und Ausgabedateien, Assemblys und Debug steuern und Präprozessor. Jede Option steht in zwei austauschbar Formen: `-``option` und `/``option`. Diese Dokumentation zeigt nur die `/``option` Form.  
  
 Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
|Beschreibung|Verwendung|  
|--------|---------|  
|Kompilieren Sie "File.vb" verwenden und Erstellen von File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Kompilieren Sie "File.vb" verwenden, und Erstellen von File.dll.|`vbc /target:library File.vb`|  
|Kompilieren Sie "File.vb" verwenden und Erstellen von My.exe|`vbc /out:My.exe File.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und `DEBUG` Symbol definiert ist, erzeugt File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von File2.dll ohne das Logo oder Warnungen anzeigen|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis zu Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 Beim Kompilieren von der Befehlszeile aus müssen Sie explizit die Microsoft verweisen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Laufzeit-Bibliothek über die `/reference` -Compileroption.  
  
> [!TIP]
>  Beim Erstellen eines Projekts mit Visual Studio-IDE können Sie Informationen zum zugehörigen anzeigen **Vbc** mit seiner Compileroptionen im Fenster "Ausgabe". Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder ein höheres Maß an Ausführlichkeit. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
