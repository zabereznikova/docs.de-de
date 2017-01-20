---
title: "Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30310"
  - "bc30310"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30310"
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die `System.MarshalByRefObject`\-Klasse ermöglicht Anwendungen, die Remotezugriff unterstützen, über die Grenzen von Anwendungsdomänen hinweg auf Objekte zugreifen zu können.  Typen müssen von der `MarshalByRejectObject`\-Klasse erben, wenn sie über Anwendungsdomänengrenzen hinweg verwendet werden.  Der Zustand des Objekts darf nicht kopiert werden, da die Member des Objekts außerhalb der Anwendungsdomäne, in der sie erstellt wurden, nicht verwendet werden können.  
  
 **Fehler\-ID:** BC30310  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie den Verweis, um sicherzustellen, dass der Member, auf den verwiesen wird, gültig ist.  
  
2.  Qualifizieren Sie den Member explizit mit dem `Me`\-Schlüsselwort.  
  
## Siehe auch  
 <xref:System.MarshalByRefObject>   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)