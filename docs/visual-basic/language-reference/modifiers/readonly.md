---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ca1d2e4eddb3b88073d6fcd46b0de5c627ba809
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Gibt an, dass eine Variable oder die Eigenschaft lesen aber nicht geschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `ReadOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `ReadOnly` Element muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `ReadOnly` zusammen mit `Static` in der gleichen Deklaration.  
  
-   **Zuweisen eines Werts an.** Code, in dem eine `ReadOnly` Eigenschaft der Wert kann nicht festgelegt werden. Code, der auf den zugrunde liegenden Speicher zugreifen kann jedoch zuweisen oder ändern Sie den Wert zu einem beliebigen Zeitpunkt.  
  
     Sie können einen Wert zuweisen einer `ReadOnly` Variable nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur, die in der sie definiert ist.  
  
## <a name="when-to-use-a-readonly-variable"></a>Eine schreibgeschützte Variable zu verwenden  
 Es gibt Situationen, in dem Sie können nicht mit, einem [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts. Z. B. die `Const` Anweisung möglicherweise nicht übernehmen den Datentyp, die Sie zuweisen möchten, oder Sie können möglicherweise nicht den Wert zum Zeitpunkt der Kompilierung mit einem konstanten Ausdruck zu berechnen. Sie bemerken möglicherweise nicht auch den Wert zum Zeitpunkt der Kompilierung. In diesen Fällen können Sie eine `ReadOnly` Variable verweist, einen konstanten Wert enthält.  
  
> [!IMPORTANT]
>  Der Datentyp der Variablen ein Verweistyp, wie z. B. ein Array oder eine Klasseninstanz ist ihre Member können geändert werden, auch wenn die Variable selbst ist `ReadOnly`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Bei der Initialisierung, das Array verweist `characterArray()` enthält "X", "y" und "Z". Da die Variable `characterArray` ist `ReadOnly`, dessen Wert kann nicht geändert werden, sobald er initialisiert wurde, die; nicht möglich, weisen Sie ein neues Array zu. Allerdings können Sie die Werte von mindestens einer der Array-Elemente ändern. Nach einem Aufruf an die Prozedur `changeArrayElement`, das Array verweist `characterArray()` enthält "X", "M" und "Z".  
  
 Beachten Sie, dass dies deklarieren einen Prozedurparameter werden ähnelt [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), die verhindert, dass der Prozedur das aufrufende Argument selbst zu ändern, jedoch kann er seine Mitglieder ändern.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `ReadOnly` -Eigenschaft für das Datum, an dem ein Mitarbeiter eingestellt wurde. Die Klasse speichert den Eigenschaftswert intern als eine `Private` Variable, und nur Code innerhalb der Klasse kann diesen Wert ändern. Die Eigenschaft ist jedoch `Public`, und jeglicher Code, der die Klasse zugreifen kann, kann die Eigenschaft lesen.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
