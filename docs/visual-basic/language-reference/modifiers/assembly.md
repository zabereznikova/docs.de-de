---
title: "Assembly (Visual Basic) | Microsoft Docs"
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
  - "vb.Assembly"
  - "vb.AssemblyAttribute"
  - "Assembly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Assembly modifier"
  - "Assembly keyword"
  - "attribute blocks, Assembly keyword"
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Assembly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass ein Attribut am Anfang einer Quelldatei für die ganze Assembly gilt.  
  
## Hinweise  
 Viele Attribute betreffen ein einzelnes Programmierelement, z. B. eine Klasse oder eine Eigenschaft.  Ein solches Attribut wird angewendet, indem der Attributblock innerhalb spitzer Klammern \(`< >`\) direkt an die Deklarationsanweisung angehängt wird.  
  
 Wenn ein Attribut nicht nur das folgende Element, sondern die gesamte Assembly betrifft, stellen Sie den Attributblock an den Anfang der Quelldatei und kennzeichnen das Attribut mit dem `Assembly`\-Schlüsselwort.  Wenn das Attribut für das aktuelle Assemblymodul gilt, verwenden Sie das [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md)\-Schlüsselwort.  
  
 Sie können ein Attribut auch auf eine Assembly in der Datei AssemblyInfo.vb anwenden. In diesem Fall muss kein Attributblock in der Hauptquellcodedatei verwendet werden.  
  
## Siehe auch  
 [Module \<keyword\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)