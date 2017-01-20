---
title: "Overridable (Visual Basic) | Microsoft Docs"
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
  - "Overridable"
  - "vb.Overridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elements, concrete"
  - "properties [Visual Basic], redefining"
  - "overriding, Overridable keyword"
  - "elements, virtual"
  - "virtual elements"
  - "procedures, overriding"
  - "concrete elements"
  - "procedures, redefining"
  - "Overridable keyword"
  - "properties [Visual Basic], overriding"
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass eine Eigenschaft oder eine Prozedur von einer identisch benannten Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.  
  
## Hinweise  
 Der `Overridable`\-Modifizierer kann eine Eigenschaft oder eine Methode in einer in einer abgeleiteten Klasse überschrieben werden, um Klasse.  Der [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)\-Modifizierer hat zur Folge, dass eine Eigenschaft oder eine Methode in einer abgeleiteten Klasse überschrieben wird.  Weitere Informationen finden Sie unter [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn der `Overridable` oder `NotOverridable`\-Modifizierer nicht angegeben, ist die Standardeinstellung, hängt davon ab, ob die Eigenschaft oder Methode der Basisklasse eine Eigenschaft oder eine Methode überschreibt.  Wenn die Eigenschaft oder Methode der Basisklasse eine Eigenschaft oder eine Methode überschreibt, ist die Standardeinstellung `Overridable`. andernfalls ist es `NotOverridable`.  
  
 Sowohl mit Shadowing als auch mit Überschreiben kann ein geerbtes Element neu definiert werden. Es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.  Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Ein Element, das überschrieben werden kann, wird manchmal als *virtuelles* Element bezeichnet.  Wenn es überschrieben werden kann, aber nicht überschrieben werden muss, wird es auch manchmal als *konkretes* Element bezeichnet.  
  
 Sie können `Overridable` nur in einer Deklarationsanweisung für eine Eigenschaft oder Prozedur verwenden.  
  
## Kombinierte Modifizierer  
 Sie können `Overridable` oder `NotOverridable` für eine `Private`\-Methode angeben.  
  
 `Overridable` kann nicht zusammen mit `MustOverride`, `NotOverridable` oder `Shared` in derselben Deklaration verwendet werden.  
  
 Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides`kombinieren.  
  
## Verwendung  
 Der `Overridable`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Modifiers](../../../visual-basic/language-reference/modifiers/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)