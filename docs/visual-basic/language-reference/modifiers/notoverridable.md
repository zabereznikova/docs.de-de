---
title: "NotOverridable (Visual Basic) | Microsoft Docs"
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
  - "vb.NotOverridable"
  - "NotOverridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sealed methods"
  - "NotOverridable keyword"
  - "properties [Visual Basic], redefining"
  - "elements, sealed"
  - "sealed elements"
  - "procedures, overriding"
  - "procedures, redefining"
  - "overriding"
  - "methods [Visual Basic], sealed"
  - "properties [Visual Basic], overriding"
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# NotOverridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse nicht überschrieben werden kann.  
  
## Hinweise  
 Der `NotOverridable`\-Modifizierer hat zur Folge, dass eine Eigenschaft oder eine Methode in einer abgeleiteten Klasse überschrieben wird.  Der [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)\-Modifizierer kann eine Eigenschaft oder eine Methode in einer in einer abgeleiteten Klasse überschrieben werden, um Klasse.  Weitere Informationen finden Sie unter [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn der `Overridable` oder `NotOverridable`\-Modifizierer nicht angegeben, ist die Standardeinstellung, hängt davon ab, ob die Eigenschaft oder Methode der Basisklasse eine Eigenschaft oder eine Methode überschreibt.  Wenn die Eigenschaft oder Methode der Basisklasse eine Eigenschaft oder eine Methode überschreibt, ist die Standardeinstellung `Overridable`. andernfalls ist es `NotOverridable`.  
  
 Ein Element, das nicht überschrieben werden kann, wird auch als *versiegeltes* Element bezeichnet.  
  
 Sie können `NotOverridable` nur in einer Deklarationsanweisung für eine Eigenschaft oder Prozedur verwenden.  Sie können `NotOverridable` nur für eine Eigenschaft oder Prozedur festlegen, die eine andere Eigenschaft oder Prozedur überschreibt, also nur in Kombination mit `Overrides`.  
  
## Kombinierte Modifizierer  
 Sie können `Overridable` oder `NotOverridable` für eine `Private`\-Methode angeben.  
  
 `NotOverridable` kann nicht zusammen mit `MustOverride`, `Overridable` oder `Shared` in derselben Deklaration verwendet werden.  
  
## Verwendung  
 Der `NotOverridable`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Modifiers](../../../visual-basic/language-reference/modifiers/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)