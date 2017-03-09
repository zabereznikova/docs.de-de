---
title: "ReadOnly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ReadOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ReadOnly keyword"
  - "variables [Visual Basic], read-only"
  - "ReadOnly property"
  - "properties [Visual Basic], read-only"
  - "read-only variables"
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ReadOnly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Legt fest, dass eine Variable oder Eigenschaft schreibgeschützt ist, also nur gelesen, aber nicht geschrieben werden kann.  
  
## Hinweise  
  
## Regeln  
  
-   **Deklarationskontext.** `ReadOnly` kann nur auf Modulebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für ein `ReadOnly`\-Element eine Klasse, eine Struktur oder ein Modul sein muss und keine Quelldatei, kein Namespace und keine Prozedur sein kann.  
  
-   **Kombinierte Modifizierer.** Sie können `ReadOnly` nicht zusammen mit `Static` in derselben Deklaration angeben.  
  
-   **Zuweisen von Werten.** Code, in dem eine `ReadOnly`\-Eigenschaft verwendet wird, kann deren Wert nicht festlegen.  Jedoch kann Code, der Zugriff auf den zugrunde liegenden Speicher hat, den Wert jederzeit zuweisen oder ändern.  
  
     Sie können einer `ReadOnly`\-Variablen nur in ihrer Deklaration oder im Konstruktor der Klasse oder Struktur, in der sie definiert ist, einen Wert zuweisen.  
  
## Verwenden einer ReadOnly\-Variablen  
 Es gibt Situationen, in denen Sie keine [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen.  Beispielsweise ist es möglich, dass die `Const`\-Anweisung den Datentyp, den Sie zuweisen möchten, nicht akzeptiert, oder dass der Wert während des Kompilierens nicht mit einem konstanten Ausdruck berechnet werden kann.  Möglicherweise ist der Wert zur Kompilierungszeit nicht einmal bekannt.  In diesen Fällen können Sie eine `ReadOnly`\-Variable zum Speichern eines konstanten Werts verwenden.  
  
> [!IMPORTANT]
>  Falls es sich beim Datentyp der Variablen um einen Verweistyp handelt, etwa ein Array oder eine Klasseninstanz, dann können dessen bzw. deren Member auch dann geändert werden, wenn die Variable selbst als `ReadOnly` deklariert wurde.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Nach seiner Initialisierung enthält das Array, auf das `characterArray()` zeigt, die Werte "x", "y" und "z".  Weil die `characterArray`\-Variable als `ReadOnly` deklariert wurde, können Sie ihren Wert nach ihrer Initialisierung nicht ändern; d. h. Sie können ihr kein anderes Array zuweisen.  Sie können jedoch die Werte von einem oder mehreren Arraymember\(n\) ändern.  Nach einem Aufruf der Prozedur `changeArrayElement` enthält das Array, auf das `characterArray()` zeigt, die Werte "x", "M" und "z".  
  
 Beachten Sie, dass dies der Deklaration eines Prozedurparameters als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) ähnlich ist. Diese Deklaration bewirkt, dass die Prozedur zwar nicht das Aufrufargument, aber dessen Member verändern kann.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `ReadOnly`\-Eigenschaft für das Einstellungsdatum eines Mitarbeiters definiert.  In der Klasse wird der Eigenschaftswert intern als `Private`\-Variable gespeichert, und nur Code innerhalb der Klasse kann diesen Wert ändern.  Die Eigenschaft ist jedoch als `Public` deklariert, und jeder Code, der auf die Klasse zugreifen kann, kann die Eigenschaft lesen.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/visualbasic/readonly_1.vb)]  
  
 Der `ReadOnly`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim\-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Siehe auch  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)