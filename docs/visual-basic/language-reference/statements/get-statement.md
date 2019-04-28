---
title: Get-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 245d2cc36abde76a8f8bd73bae5d7ede183d4d03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638024"
---
# <a name="get-statement"></a>Get-Anweisung
Deklariert eine `Get` Eigenschaftenprozedur, um den Wert einer Eigenschaft abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional Klicken Sie auf höchstens die `Get` und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:<br /><br /> -   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen, die beim Ausführen der `Get` -Eigenschaftenprozedur aufgerufen.|  
|`End Get`|Erforderlich. Beendet die Definition der `Get` Eigenschaftenprozedur.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft müssen einen `Get` Eigenschaftenprozedur, wenn die Eigenschaft markiert ist `WriteOnly`. Die `Get` Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurückzugeben.  
  
 Visual Basic automatisch ruft einer Eigenschaft des `Get` Verfahren, wenn ein Ausdruck den Wert der Eigenschaft anfordert.  
  
 Der Hauptteil der Deklaration der Eigenschaft darf nur der Eigenschaft des `Get` und `Set` Prozeduren zwischen der [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) und `End Property` Anweisung. Es kann nicht als diese Prozeduren gespeichert werden. Insbesondere kann nicht der aktuelle Eigenschaftswert speichern. Sie müssen diesen Wert außerhalb der Eigenschaft speichern, da Wenn Sie es in einer der Eigenschaftenprozeduren speichern, die andere Eigenschaftenprozedur nicht darauf zugreifen kann. Der übliche Ansatz ist zum Speichern des Werts in einem [Private](../../../visual-basic/language-reference/modifiers/private.md) Variable, die auf derselben Ebene wie die Eigenschaft deklariert. Definieren Sie eine `Get` -Prozedur in der Eigenschaft, die auf die es angewendet.  
  
 Die `Get` Prozedur standardmäßig auf die Zugriffsebene der enthaltenden Eigenschaft auf, es sei denn, Sie verwenden `accessmodifier` in die `Get` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
- **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert ist `Friend`, Sie können deklarieren, die `Get` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `ReadOnly` -Eigenschaft, die `Get` Prozedur darstellt, die gesamte Eigenschaft. Sie können nicht deklarieren eine andere Zugriffsebene für `Get`, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
- **Der Rückgabetyp.** Die [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) können deklarieren, den den Datentyp des zurückgegebenen Werts. Die `Get` Prozedur gibt, dass der Datentyp automatisch zurück. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn die `Property` Anweisung gibt keinen `returntype`, gibt die Prozedur `Object`.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zurückgeben aus einer Prozedur.** Wenn die `Get` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, in der Anweisung, die den Wert der Eigenschaft angefordert.  
  
     `Get` Property-Prozeduren können einen Wert, der mit Zurückgeben der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder den Eigenschaftennamen den zurückgegeben Wert zuweisen. Weitere Informationen finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
- **Der Rückgabewert.** Zum Zurückgeben eines Werts aus einer `Get` Verfahren, Sie können entweder weisen Sie den Wert an den Eigenschaftennamen oder nehmen Sie diese in einem [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md). Die `Return` gleichzeitig delegatenvariablen die `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur.  
  
     Bei Verwendung von `Exit Property` ohne einen zugewiesenen Wert an den Eigenschaftennamen der `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück. Weitere Informationen finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Das folgende Beispiel veranschaulicht zwei Möglichkeiten, die schreibgeschützte Eigenschaft `quoteForTheDay` kann den Wert in die private Variable zurückgeben `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Get` Anweisung, um den Wert einer Eigenschaft zurück.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Exemplarische Vorgehensweise: Definieren von Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
