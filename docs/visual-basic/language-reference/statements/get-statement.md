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
ms.openlocfilehash: d6a6fdfd191de76871619dea3bd1794b487698aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605107"
---
# <a name="get-statement"></a>Get-Anweisung
Deklariert eine `Get` -Eigenschaftenprozedur verwendet, um den Wert einer Eigenschaft abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional für höchstens eine der `Get` und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:<br /><br /> -   [Geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen, die beim Ausführen der `Get` -Eigenschaftenprozedur aufgerufen wird.|  
|`End Get`|Erforderlich. Beendet die Definition des der `Get` -Eigenschaftenprozedur.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft benötigen eine `Get` Eigenschaftenprozedur, solange die Eigenschaft `WriteOnly`. Die `Get` Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurück.  
  
 Visual Basic automatisch ruft einer Eigenschaft `Get` Prozedur, wenn ein Ausdruck den Wert der Eigenschaft anfordert.  
  
 Der Hauptteil der Deklaration der Eigenschaft kann nur der Eigenschaft enthalten `Get` und `Set` Prozeduren zwischen den [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) und die `End Property` Anweisung. Es kann keine etwas anderes als diese Prozeduren speichern. Es kann nicht insbesondere aktuellen Wert der Eigenschaft gespeichert. Dieser Wert außerhalb der Eigenschaft müssen gespeichert werden, da, wenn Sie es in eine der Eigenschaftenprozeduren speichern, die andere Eigenschaftenprozedur nicht darauf zugreifen kann. Die übliche Vorgehensweise wird zum Speichern des Werts in einer [Private](../../../visual-basic/language-reference/modifiers/private.md) Variable, die auf derselben Ebene wie die Eigenschaft deklariert. Definieren Sie eine `Get` -Prozedur in der Eigenschaft, für die er gilt.  
  
 Die `Get` Prozedur wird standardmäßig auf die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der `Get` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn in diesem Fall muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert wird `Friend`, Sie können deklarieren, die `Get` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `ReadOnly` -Eigenschaft, die `Get` Prozedur die gesamte Eigenschaft dar. Kann nicht deklariert eine unterschiedliche Zugriffsberechtigungen für `Get`, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
-   **Der Rückgabetyp.** Die [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) können deklarieren, den den Datentyp des zurückgegebenen Werts. Die `Get` -Prozedur gibt diesen Datentyp automatisch zurück. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn die `Property` Anweisung gibt keinen `returntype`, gibt die Prozedur `Object`.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Rückgabe aus einer Prozedur.** Wenn die `Get` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, in der Anweisung, die den Wert der Eigenschaft angefordert.  
  
     `Get` Eigenschaftenprozeduren können mit entweder einen Wert zurückgeben der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder indem Sie den Namen der Eigenschaft den zurückgegeben Wert zuweisen. Weitere Informationen finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
-   **Der Rückgabewert.** Zurückzugebenden einen Wert aus einer `Get` Prozedur, Sie können entweder weisen den Namen der Eigenschaft den Wert oder fügen Sie ihn in ein [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md). Die `Return` gleichzeitig delegatenvariablen die `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur.  
  
     Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts des Eigenschaftennamens den `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück. Weitere Informationen finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Das folgende Beispiel veranschaulicht zwei Möglichkeiten, die schreibgeschützte Eigenschaft `quoteForTheDay` kann den Wert in der privaten Variablen zurückgeben `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Get` Anweisung, um den Wert einer Eigenschaft zurückzugeben.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Exemplarische Vorgehensweise: Definieren von Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
