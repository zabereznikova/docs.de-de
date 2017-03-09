---
title: "Beispiele f&#252;r Kompilierungsbefehlszeilen (Visual&#160;Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Befehlszeile, Compiler"
  - "Kompilierung, Befehlszeilen"
  - "Befehlszeilencompiler"
  - "Kompilieren von Quellcode, über Befehlszeile"
  - "Visual Basic-Compiler, Beispielbefehlszeilen"
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Beispiele f&#252;r Kompilierungsbefehlszeilen (Visual&#160;Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Neben der Kompilierung von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programmen in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] haben Sie auch die Möglichkeit, ausführbare Dateien \(.exe\) oder Dynamic Link Library\-Dateien \(.dll\) von der Befehlszeile aus zu kompilieren.  
  
 Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen zur Steuerung von Eingabe\- und Ausgabedateien, Assemblys sowie Debug\- und Präprozessoroptionen.  Jede Option liegt in zwei austauschbaren Varianten vor: `-``option` und `/``option`.  In dieser Dokumentation wird nur die Variante `/``option` dargestellt.  
  
 Die folgende Tabelle enthält eine Liste mit Beispielbefehlszeilen, die Sie nach Bedarf abwandeln können.  
  
|To|Verwendung|  
|--------|----------------|  
|Kompilieren von **File.vb** und Erstellen von **File.exe**.|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Kompilieren von **File.vb** und Erstellen von **File.dll**.|`vbc /target:library File.vb`|  
|Kompilieren von **File.vb** und Erstellen von **My.exe**.|`vbc /out:My.exe File.vb`|  
|Kompilieren aller [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien des aktuellen Verzeichnisses mit aktivierter Optimierung und definiertem `DEBUG`\-Symbol zum Erstellen von File2.exe.|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Kompilieren aller [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien im aktuellen Verzeichnis zum Erstellen einer Debugversion von File2.dll ohne das Logo oder Warnungen anzuzeigen.|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Kompilieren aller [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien im aktuellen Verzeichnis zu Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 Beim Kompilieren von der Befehlszeile aus müssen Sie mit der `/reference`\-Compileroption explizit auf die Laufzeitbibliothek von Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verweisen.  
  
> [!TIP]
>  Wenn Sie ein Projekt erstellen, indem Sie die Visual Studio\-IDE verwenden, können Sie Informationen zum zugeordneten **vbc** Befehl mit seinen Compileroptionen im Ausgabefenster anzeigen.  Um diese Informationen anzuzeigen, öffnen Sie [Optionen \(Dialogfeld\), Projekte und Projektmappen, Erstellen und Ausführen](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann **Ausführlichkeit der MSBuild\-Projektbuildausgabe** zu **Normal** oder eine höhere Ebene des Ausführlichkeitsgrads fest.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md).  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)