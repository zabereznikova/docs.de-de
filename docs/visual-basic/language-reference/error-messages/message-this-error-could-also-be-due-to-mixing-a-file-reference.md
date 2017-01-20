---
title: "&lt;Meldung&gt; Dieser Fehler k&#246;nnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly „&lt;Assemblyname&gt;“ zur&#252;ckzuf&#252;hren sein. | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30971"
  - "vbc30971"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30971"
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Meldung&gt; Dieser Fehler k&#246;nnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly „&lt;Assemblyname&gt;“ zur&#252;ckzuf&#252;hren sein.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

\<Meldung\> Dieser Fehler könnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly „\<Assemblyname\>“ zurückzuführen sein. Ersetzen Sie in diesem Fall den Dateiverweis auf „\<Assemblydateiname\>“ in Projekt „\<Projektname1\>“ durch einen Projektverweis auf „\<Projektname2\>“.  
  
 Code in Ihrem Projekt greift auf einen Member eines anderen Projekts zu, aufgrund der Konfiguration Ihrer Projektmappe kann der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler den Verweis aber nicht auflösen.  
  
 Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler einen Verweis auf diese Assembly. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler\-ID:** BC30971  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2.  Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## Siehe auch  
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB: Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Problembehandlung bei fehlerhaften Verweisen](/visual-studio/ide/troubleshooting-broken-references)