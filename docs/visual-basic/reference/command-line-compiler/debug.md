---
title: "/debug (Visual Basic) | Microsoft Docs"
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
  - "debug compiler switches"
  - "/debug compiler option [Visual Basic]"
  - "-debug compiler option [Visual Basic]"
  - "debug compiler option [Visual Basic]"
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /debug (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Bewirkt, dass der Compiler Debuginformationen erstellt und in die Ausgabeidatei\(en\) platziert.  
  
## Syntax  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`+`  &#124; `-`|Optional.  Wenn Sie `+` oder `/debug` angeben, generiert der Compiler Debuginformationen und platziert diese in einer PDB\-Datei.  Die Angabe von `-` hat die gleiche Wirkung wie das Nichtangeben von `/debug`.|  
|`full`  &#124; `pdbonly`|Optional.  Gibt die Art der vom Compiler generierten Debuginformationen an.  Wenn Sie `/debug:pdbonly` nicht angeben, lautet die Standardeinstellung `full`. Diese Einstellung ermöglicht Ihnen, einen Debugger an das ausgeführte Programm anzuhängen.  Das `pdbonly`\-Argument ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet wird. Code der Assemblersprache wird jedoch nur angezeigt, wenn das ausgeführte Programm an den Debugger gehängt wird.|  
  
## Hinweise  
 Verwenden Sie diese Option zum Erstellen von Debugbuilds.  Wenn Sie `/debug`, `/debug+` oder `/debug:full` nicht angeben, können Sie die Ausgabedatei des Programms nicht debuggen.  
  
 Standardmäßig werden Debuginformationen nicht ausgegeben \(`/debug-`\).  Wenn Debuginformationen ausgegeben werden sollen, geben Sie `/debug` oder `/debug+` an.  
  
 Weitere Informationen zum Konfigurieren der Debugleistung einer Anwendung finden Sie unter [Erleichtern des Debuggens für ein Abbild](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
||  
|-|  
|So legen Sie \/debug in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus, und klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert im Feld **Debuginfo generieren**.|  
  
## Beispiel  
 Im folgenden Beispiel werden Debuginformationen in der Ausgabedatei `App.exe` abgelegt.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)