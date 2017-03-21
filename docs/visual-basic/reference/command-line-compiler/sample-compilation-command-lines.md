---
title: "Beispiele für Kompilierungsbefehlszeilen (Visual Basic) | Microsoft-Dokumentation"
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 918787b3377f2e5a636a6b098046ac2f455efcdd
ms.lasthandoff: 03/13/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
Als Alternative zum Kompilieren von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Programmen in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], können Sie die Kompilierung von der Befehlszeile aus, ausführbare Dateien (.exe) oder Dynamic Link Library (DLL) Dateien.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen zur Steuerung von Eingabe-und Ausgabedateien, Assemblys und Debug und Präprozessor Optionen. Jede Option liegt in zwei austauschbaren Varianten: `-``option` und `/``option`. In dieser Dokumentation wird nur die `/``option` Form.  
  
 Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
|Beschreibung|Verwendung|  
|--------|---------|  
|VB-Datei zu kompilieren und Erstellen von File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|VB-Datei zu kompilieren und Erstellen von File.dll.|`vbc /target:library File.vb`|  
|VB-Datei zu kompilieren und Erstellen von My.exe|`vbc /out:My.exe File.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und `DEBUG` -Symbol File2.exe erzeugen|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis befindet, erzeugen eine Debugversion von File2.dll erstellt wird, ohne das Logo oder Warnungen|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis zu Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 Beim Kompilieren von der Befehlszeile aus müssen Sie explizit verweisen, auf die Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Laufzeitbibliothek über die `/reference` -Compileroption.  
  
> [!TIP]
>  Wenn Sie ein Projekt mithilfe von Visual Studio-IDE erstellen, können Sie Informationen zum zugehörigen anzeigen **Vbc** Befehl seine Compileroptionen im Ausgabefenster. Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder eine höhere Stufe der Ausführlichkeit. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
