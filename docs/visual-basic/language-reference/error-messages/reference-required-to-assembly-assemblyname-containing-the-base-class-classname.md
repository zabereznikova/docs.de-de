---
title: "Ein Verweis auf die Assembly „&lt;Assemblyname&gt;“, die die Basisklasse „&lt;Klassenname&gt;“ enth&#228;lt, ist erforderlich. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30007"
  - "vbc30007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30007"
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Ein Verweis auf die Assembly „&lt;Assemblyname&gt;“, die die Basisklasse „&lt;Klassenname&gt;“ enth&#228;lt, ist erforderlich.
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Verweis auf die Assembly „\<Assemblyname\>“, die die Basisklasse „\<Klassenname\>“ enthält, ist erforderlich. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Klasse ist in einer Dynamic Link Library \(DLL\) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehreren DLLs oder Assemblys definiert ist.  
  
 **Fehler\-ID:** BC30007  
  
### So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## Siehe auch  
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [Problembehandlung bei fehlerhaften Verweisen](/visual-studio/ide/troubleshooting-broken-references)