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
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965423"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Gibt an, dass eine Variable oder Eigenschaft gelesen, aber nicht geschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
  
- **Deklarations Kontext.** Sie können `ReadOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations `ReadOnly` Kontext für ein-Element eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.  
  
- **Kombinierte modifiziererer.** Sie können nicht `ReadOnly` mit `Static` in der gleichen Deklaration angeben.  
  
- **Zuweisen eines Werts.** Code, der `ReadOnly` eine Eigenschaft beansprucht, kann seinen Wert nicht festlegen. Code, der Zugriff auf den zugrunde liegenden Speicher hat, kann den Wert jedoch jederzeit zuweisen oder ändern.  
  
     Sie können einer `ReadOnly` Variablen einen Wert nur in der Deklaration oder im Konstruktor einer Klasse oder Struktur zuweisen, in der Sie definiert ist.  
  
## <a name="when-to-use-a-readonly-variable"></a>Verwendung einer schreibgeschützten Variablen  
 Es gibt Situationen, in denen Sie keine Konstanten- [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) verwenden können, um einen konstanten Wert zu deklarieren und zuzuweisen. Beispielsweise akzeptiert die `Const` -Anweisung möglicherweise nicht den Datentyp, den Sie zuweisen möchten, oder Sie können den Wert möglicherweise nicht zur Kompilierzeit mit einem konstanten Ausdruck berechnen. Möglicherweise wissen Sie den Wert zum Zeitpunkt der Kompilierung nicht einmal. In diesen Fällen können Sie eine `ReadOnly` Variable verwenden, um einen konstanten Wert zu speichern.  
  
> [!IMPORTANT]
> Wenn der Datentyp der Variablen ein Referenztyp ist, z. b. ein Array oder eine Klasseninstanz, können die Member auch dann geändert werden, wenn `ReadOnly`die Variable selbst ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Bei der Initialisierung `characterArray()` enthält das Array, auf das verweist, "x", "y" und "z". Da die Variable `characterArray` ist `ReadOnly`, können Sie Ihren Wert nicht ändern, nachdem Sie initialisiert wurde, d. h., Sie können kein neues Array zuweisen. Sie können jedoch die Werte von einem oder mehreren Arraymembern ändern. Im Anschluss an einen aufzurufenden Vorgang `changeArrayElement` `characterArray()` enthält das Array, auf das verweist, das Zeichen "x", "M" und "z".  
  
 Beachten Sie, dass dies dem Deklarieren eines Prozedur Parameters als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)ähnelt, wodurch verhindert wird, dass die Prozedur das aufrufende Argument selbst ändert, aber seine Member ändern kann.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `ReadOnly` -Eigenschaft für das Datum definiert, an dem ein Mitarbeiter eingestellt wurde. Die-Klasse speichert den Eigenschafts Wert intern `Private` als Variable, und nur Code in der Klasse kann diesen Wert ändern. Die-Eigenschaft ist `Public`jedoch, und jeder Code, der auf die-Klasse zugreifen kann, kann die-Eigenschaft lesen.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 Der `ReadOnly`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
