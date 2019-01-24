---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 741374cc375e33868239161af23a38af7680b290
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684066"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Gibt an, dass eine Variable oder Eigenschaft lesen aber nicht geschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `ReadOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `ReadOnly` Element muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `ReadOnly` zusammen mit `Static` in der gleichen Deklaration.  
  
-   **Zuweisen eines Werts an.** Code, in dem eine `ReadOnly` Eigenschaft kann nicht den Wert festgelegt. Code, der auf den zugrunde liegenden Speicher zugreifen kann jedoch zuweisen oder den Wert jederzeit ändern.  
  
     Sie können einen Wert zuweisen einer `ReadOnly` Variable nur in der Deklaration oder in den Konstruktor einer Klasse oder Struktur, in dem es definiert ist.  
  
## <a name="when-to-use-a-readonly-variable"></a>Eine schreibgeschützte Variable zu verwenden  
 Es gibt Situationen, in dem Sie können nicht mit, einem [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) zu deklarieren und Zuweisen eines konstanten Werts. Z. B. die `Const` -Anweisung kann nicht übernehmen den Datentyp, die Sie zuweisen möchten, oder Sie möglicherweise nicht in der Lage, den Wert zum Zeitpunkt der Kompilierung mit einem konstanten Ausdruck zu berechnen. Möglicherweise wissen Sie nicht auch den Wert zum Zeitpunkt der Kompilierung. In diesen Fällen können Sie eine `ReadOnly` Variable, einen konstanten Wert enthalten soll.  
  
> [!IMPORTANT]
>  Der Datentyp der Variablen ein Verweistyp, wie z. B. ein Array oder eine Klasseninstanz ist ihre Member können geändert werden, wenn die Variable selbst `ReadOnly`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Bei der Initialisierung, das Array verweist `characterArray()` enthält "X", "y" und "Z". Da die Variable `characterArray` ist `ReadOnly`, Wert nicht ändern, nachdem es initialisiert wird, das ist; Sie können nicht es ein neues Array zuweisen. Allerdings können Sie die Werte von mindestens einer der Arraymember ändern. Nach einem Aufruf an die Prozedur `changeArrayElement`, das Array verweist `characterArray()` enthält "X", "M" und "Z".  
  
 Beachten Sie, dass dies ähnelt der Deklaration eines Prozedurparameters sein [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), die verhindert, dass der Prozedur das aufrufende Argument selbst zu ändern, aber seine Mitglieder ändern kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `ReadOnly` -Eigenschaft für das Datum, an dem ein Mitarbeiter eingestellt wurde. Die Klasse speichert den Eigenschaftswert intern als eine `Private` Variable, und nur Code innerhalb der Klasse kann diesen Wert ändern. Die Eigenschaft ist allerdings `Public`, und jeder Code, der die Klasse zugreifen kann, kann die Eigenschaft lesen.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
