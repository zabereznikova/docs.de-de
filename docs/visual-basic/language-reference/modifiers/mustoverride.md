---
title: "MustOverride (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.MustOverride"
  - "MustOverride"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "virtual elements, pure"
  - "elements, pure virtual"
  - "properties [Visual Basic], redefining"
  - "procedures, overriding"
  - "overriding, MustOverride keyword"
  - "procedures, redefining"
  - "pure virtual elements"
  - "MustOverride keyword"
  - "properties [Visual Basic], overriding"
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# MustOverride (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass eine Eigenschaft oder Prozedur in dieser Klasse nicht implementiert ist und in einer abgeleiteten Klasse überschrieben werden muss, bevor sie verwendet werden kann.  
  
## Hinweise  
 Sie können `MustOverride` nur in einer Deklarationsanweisung für eine Eigenschaft oder Prozedur verwenden.  Die Eigenschaft oder Prozedur, mit der `MustOverride` angegeben wird, muss ein Member einer Klasse sein, und die Klasse muss mit [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md) markiert sein.  
  
## Regeln  
  
-   **Unvollständige Deklaration.** Wenn Sie `MustOverride` angeben, geben Sie für die Eigenschaft oder Prozedur keine zusätzlichen Codezeilen an, auch nicht die Anweisungen `End Function`, `End Property` und `End Sub`.  
  
-   **Kombinierte Modifizierer.** `MustOverride` kann nicht zusammen mit `NotOverridable`, `Overridable` oder `Shared` in derselben Deklaration verwendet werden.  
  
-   **Shadowing und Überschreiben.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.  Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Andere Bezeichnungen.** Ein Element, das nur in einer Überschreibung verwendet werden kann, wird gelegentlich auch als *rein virtuelles* Element bezeichnet.  
  
 Der `MustOverride`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)