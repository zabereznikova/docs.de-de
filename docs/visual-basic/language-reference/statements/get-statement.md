---
title: Get-Anweisung
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
ms.openlocfilehash: 9560faf90d531c32f104dbd053a7c1f5584cfb1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351172"
---
# <a name="get-statement"></a>Get-Anweisung
Deklariert eine `Get`-Eigenschaften Prozedur, mit der der Wert einer Eigenschaft abgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional für höchstens eine der `Get`-und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:<br /><br /> -   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privat](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die `Get`-Eigenschaften Prozedur aufgerufen wird.|  
|`End Get`|Erforderlich Beendet die Definition der `Get`-Eigenschaften Prozedur.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft muss über eine `Get`-Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist `WriteOnly`markiert. Die `Get` Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurückzugeben.  
  
 Visual Basic automatisch die `Get` Prozedur einer Eigenschaft aufruft, wenn ein Ausdruck den Eigenschafts Wert anfordert.  
  
 Der Text der Eigenschafts Deklaration darf nur die `Get`-und `Set` Prozeduren der Eigenschaft zwischen der [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`-Anweisung enthalten. Es kann nichts anderes als diese Prozeduren speichern. Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden. Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen. Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../../../visual-basic/language-reference/modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist. Sie müssen eine `Get` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.  
  
 Die `Get` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der `Get`-Anweisung.  
  
## <a name="rules"></a>Regeln  
  
- **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene für die `Get` oder die `Set` Prozedur angeben, jedoch nicht für beide. Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft. Wenn die Eigenschaft beispielsweise als `Friend`deklariert ist, können Sie die `Get` Prozedur `Private`deklarieren, jedoch nicht `Public`.  
  
     Wenn Sie eine `ReadOnly`-Eigenschaft definieren, stellt die `Get` Prozedur die gesamte-Eigenschaft dar. Sie können für `Get`keine andere Zugriffsebene deklarieren, da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
- **Rückgabetyp.** Die [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) kann den Datentyp des zurückgegebenen Werts deklarieren. Die `Get` Prozedur gibt den Datentyp automatisch zurück. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn die `Property`-Anweisung `returntype`nicht angibt, gibt die Prozedur `Object`zurück.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zurückgeben aus einer Prozedur.** Wenn die `Get` Prozedur an den aufrufenden Code zurückkehrt, wird die Ausführung innerhalb der Anweisung fortgesetzt, die den Eigenschafts Wert angefordert hat.  
  
     `Get`-Eigenschaften Prozeduren können einen Wert zurückgeben, indem Sie entweder die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) verwenden oder den Rückgabewert dem Eigenschaftsnamen zuweisen. Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Die Anweisungen `Exit Property` und `Return` führen zu einem sofortigen Beenden einer Eigenschaften Prozedur. Eine beliebige Anzahl von `Exit Property`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Property`-und `Return`-Anweisungen mischen.  
  
- **Rückgabewert.** Um einen Wert aus einer `Get` Prozedur zurückzugeben, können Sie den Wert entweder dem Eigenschaftsnamen zuweisen oder ihn in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md)einschließen. Die `Return`-Anweisung weist gleichzeitig den Rückgabewert der `Get` Prozedur zu und beendet die Prozedur.  
  
     Wenn Sie `Exit Property` verwenden, ohne dem Eigenschaftsnamen einen Wert zuzuweisen, gibt die `Get` Prozedur den Standardwert für den Datentyp der Eigenschaft zurück. Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, wie die schreibgeschützte Eigenschaft `quoteForTheDay` den in der privaten Variablen `quoteValue`gespeicherten Wert zurückgeben kann.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Get`-Anweisung verwendet, um den Wert einer Eigenschaft zurückzugeben.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Exemplarische Vorgehensweise: Definieren von Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
