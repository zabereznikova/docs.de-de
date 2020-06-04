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
ms.openlocfilehash: 31936fb2c8f658203a43702a2b5fa4ee2481beb5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404601"
---
# <a name="get-statement"></a>Get-Anweisung
Deklariert eine- `Get` Eigenschaften Prozedur, mit der der Wert einer Eigenschaft abgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Siehe [Attribut Liste](attribute-list.md).|  
|`accessmodifier`|Optional für höchstens eine der `Get` -und- `Set` Anweisungen in dieser Eigenschaft. Kann eines der folgenden Elemente sein:<br /><br /> -   [Gebieten](../modifiers/protected.md)<br />-   [Kollegen](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die- `Get` Eigenschaften Prozedur aufgerufen wird.|  
|`End Get`|Erforderlich. Beendet die Definition der `Get` Eigenschaften Prozedur.|  
  
## <a name="remarks"></a>Bemerkungen  
 Jede Eigenschaft muss über eine `Get` Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist gekennzeichnet `WriteOnly` . Die `Get` Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurückzugeben.  
  
 Visual Basic automatisch die-Prozedur einer Eigenschaft aufruft, `Get` Wenn ein Ausdruck den Eigenschafts Wert anfordert.  
  
 Der Text der Eigenschafts Deklaration darf nur die- `Get` und- `Set` Prozeduren der Eigenschaft zwischen der- [Eigenschafts Anweisung](property-statement.md) und der- `End Property` Anweisung enthalten. Es kann nichts anderes als diese Prozeduren speichern. Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden. Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen. Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist. Sie müssen eine `Get` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.  
  
 Die `Get` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der- `Get` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
- **Gemischte Zugriffsebenen.** Wenn Sie eine Lese-/Schreibeigenschaft definieren, können Sie optional eine andere Zugriffsebene für die- `Get` oder die- `Set` Prozedur angeben, aber nicht beides. Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft. Wenn beispielsweise die-Eigenschaft deklariert wird `Friend` , können Sie die Prozedur deklarieren `Get` `Private` , jedoch nicht `Public` .  
  
     Wenn Sie eine Eigenschaft definieren `ReadOnly` , stellt die `Get` Prozedur die gesamte Eigenschaft dar. Sie können keine andere Zugriffsebene für deklarieren `Get` , da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
- **Rückgabetyp.** Die [Property-Anweisung](property-statement.md) kann den Datentyp des zurückgegebenen Werts deklarieren. Der-Datentyp wird von der `Get` Prozedur automatisch zurückgegeben. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn die- `Property` Anweisung nicht angibt `returntype` , gibt die Prozedur zurück `Object` .  
  
## <a name="behavior"></a>Verhalten  
  
- **Zurückgeben aus einer Prozedur.** Wenn die `Get` Prozedur in den aufrufenden Code zurückkehrt, wird die Ausführung innerhalb der Anweisung fortgesetzt, die den Eigenschafts Wert angefordert hat.  
  
     `Get`Eigenschaften Prozeduren können entweder mithilfe der [Return-Anweisung](return-statement.md) oder durch Zuweisen des Rückgabewerts zum Eigenschaftsnamen einen Wert zurückgeben. Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](function-statement.md).  
  
     Die `Exit Property` -und- `Return` Anweisungen führen zu einem sofortigen Beenden einer Eigenschaften Prozedur. Eine beliebige Anzahl von `Exit Property` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Property` -und- `Return` Anweisungen  
  
- **Rückgabewert.** Um einen Wert aus einer Prozedur zurückzugeben `Get` , können Sie den Wert entweder dem Eigenschaftsnamen zuweisen oder ihn in eine [Return-Anweisung](return-statement.md)einschließen. Die `Return` -Anweisung weist gleichzeitig den `Get` Rückgabewert der Prozedur zu und beendet die Prozedur.  
  
     Wenn Sie verwenden `Exit Property` , ohne dem Eigenschaftsnamen einen Wert zuzuweisen, `Get` gibt die Prozedur den Standardwert für den Datentyp der Eigenschaft zurück. Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](function-statement.md).  
  
     Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, wie die schreibgeschützte Eigenschaft `quoteForTheDay` den in der privaten Variablen gespeicherten Wert zurückgeben kann `quoteValue` .  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die- `Get` Anweisung verwendet, um den Wert einer Eigenschaft zurückzugeben.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Set-Anweisung](set-statement.md)
- [Property Statement](property-statement.md)
- [Exit-Anweisung](exit-statement.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
- [Exemplarische Vorgehensweise: Definieren von Klassen](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
