---
title: "Es ist ein Verweis auf die Assembly „&lt;Assemblyidentit&#228;t&gt;“ erforderlich, die den Typ „&lt;Typname&gt;“ enth&#228;lt, , aber aufgrund der Mehrdeutigkeit der Projekte „&lt;Projektname1&gt;“ und „&lt;Projektname2&gt;“ wurde kein geeigneter Verweis gefunden. | Microsoft Docs"
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
  - "bc30969"
  - "vbc30969"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30969"
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Es ist ein Verweis auf die Assembly „&lt;Assemblyidentit&#228;t&gt;“ erforderlich, die den Typ „&lt;Typname&gt;“ enth&#228;lt, , aber aufgrund der Mehrdeutigkeit der Projekte „&lt;Projektname1&gt;“ und „&lt;Projektname2&gt;“ wurde kein geeigneter Verweis gefunden.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Ausdruck verwendet einen Typ \(z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten\), der außerhalb des Projekts definiert ist. Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.  
  
 Die genannten Projekte erzeugen Assemblys mit demselben Namen. Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.  
  
 Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler einen Verweis auf diese Assembly. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler\-ID:** BC30969  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2.  Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## Siehe auch  
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB: Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Problembehandlung bei fehlerhaften Verweisen](/visual-studio/ide/troubleshooting-broken-references)