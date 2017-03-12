---
title: "/warnaserror (Visual Basic) | Microsoft Docs"
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
  - "warnaserror compiler option [Visual Basic]"
  - "/warnaserror compiler option [Visual Basic]"
  - "-warnaserror compiler option [Visual Basic]"
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /warnaserror (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Bewirkt, dass der Compiler eine erstmalig auftretende Warnung als Fehler behandelt.  
  
## Syntax  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|\+ &#124; \-|Optional.  Standardmäßig ist `/warnaserror-` aktiviert; Warnungen verhindern in diesem Fall nicht, dass der Compiler eine Ausgabedatei erstellt.  Die `/warnaserror` \-Option \(entspricht `/warnaserror+`\) bewirkt, dass Warnungen als Fehler behandelt werden.|  
|`numberList`|Optional.  Durch Kommas getrennte Liste der Warnungs\-ID\-Nummern, für die die `/warnaserror`\-Option gilt.  Wenn keine Warnungs\-ID angegeben wird, gilt die `/warnaserror`\-Option für alle Warnungen.|  
  
## Hinweise  
 Die Option `/warnaserror` behandelt alle Warnungen als Fehler.  Alle Meldungen, die normalerweise als Warnungen gemeldet werden, werden stattdessen als Fehler gemeldet.  Der Compiler gibt aufeinander folgende Vorkommen der gleichen Warnung als Warnungen aus.  
  
 Standardmäßig ist `/warnaserror-` aktiviert. Dies bewirkt, dass die Warnungen nur zur Information dienen.  Die `/warnaserror` \-Option \(entspricht `/warnaserror+`\) bewirkt, dass Warnungen als Fehler behandelt werden.  
  
 Wenn nur einige ausgewählte Warnungen als Fehler behandelt werden sollen, erstellen Sie eine Liste mit durch Trennzeichen voneinander getrennten Warnungsnummern, die als Fehler behandelt werden sollen.  
  
> [!NOTE]
>  Mit der `/warnaserror`\-Option wird nicht gesteuert, wie Warnungen angezeigt werden.  Verwenden Sie die [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)\-Option, um Warnungen zu deaktivieren.  
  
||  
|-|  
|So legen Sie \/warnaserror darauf fest, alle Warnungen in der Visual Studio\-IDE als Fehler zu behandeln|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass das Kontrollkästchen **Alle Warnungen deaktivieren** deaktiviert ist.<br />4.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.|  
  
||  
|-|  
|So legen Sie \/warnaserror darauf fest, bestimmte Warnungen in der Visual Studio\-IDE als Fehler zu behandeln|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Stellen Sie sicher, dass das Kontrollkästchen **Alle Warnungen deaktivieren** deaktiviert ist.<br />4.  Stellen Sie sicher, dass das Kontrollkästchen **Alle Warnungen als Fehler behandeln** deaktiviert ist.<br />5.  Wählen Sie in der Spalte **Benachrichtigung** neben der Warnung, die als Fehler behandelt werden soll, **Fehler** aus.|  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert, und der Compiler zeigt bei jeder Warnung, die zum ersten Mal auftritt, einen Fehler an.  
  
```  
vbc /warnaserror in.vb  
```  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, und nur die Warnung für nicht verwendete lokale Variablen \(42024\) wird als Fehler behandelt.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic)