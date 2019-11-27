---
title: Set-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349568"
---
# <a name="set-statement-visual-basic"></a>Set-Anweisung (Visual Basic)
Deklariert eine `Set`-Eigenschaften Prozedur, mit der einer Eigenschaft ein Wert zugewiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>-Komponenten  
 `attributelist`  
 Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Optional für höchstens eine der `Get`-und `Set` Anweisungen in dieser Eigenschaft. Einer der folgenden Werte ist möglich:  
  
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Erforderlich -Parameter, der den neuen Wert für die Eigenschaft enthält.  
  
 `datatype`  
 Erforderlich, wenn `Option Strict` `On`ist. Der Datentyp des `value`-Parameters. Der angegebene Datentyp muss mit dem Datentyp der Eigenschaft übereinstimmen, in der diese `Set` Anweisung deklariert ist.  
  
 `statements`  
 Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die `Set`-Eigenschaften Prozedur aufgerufen wird.  
  
 `End Set`  
 Erforderlich Beendet die Definition der `Set`-Eigenschaften Prozedur.  
  
## <a name="remarks"></a>Hinweise  
 Jede Eigenschaft muss über eine `Set`-Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist `ReadOnly`markiert. Die `Set` Prozedur wird verwendet, um den Wert der-Eigenschaft festzulegen.  
  
 Visual Basic automatisch die `Set` Prozedur einer Eigenschaft aufruft, wenn eine Zuweisungsanweisung einen Wert bereitstellt, der in der-Eigenschaft gespeichert werden soll.  
  
 Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften Zuweisungen. Wenn Sie keinen Parameter für `Set`bereitstellen, verwendet die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) einen impliziten Parameter mit dem Namen `value`. Der-Parameter enthält den Wert, der der-Eigenschaft zugewiesen werden soll. In der Regel speichern Sie diesen Wert in einer privaten lokalen Variable und geben ihn zurück, wenn die `Get` Prozedur aufgerufen wird.  
  
 Der Text der Eigenschafts Deklaration darf nur die `Get`-und `Set` Prozeduren der Eigenschaft zwischen der [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`-Anweisung enthalten. Es kann nichts anderes als diese Prozeduren speichern. Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden. Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen. Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../../../visual-basic/language-reference/modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist. Sie müssen eine `Set` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.  
  
 Die `Set` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der `Set`-Anweisung.  
  
## <a name="rules"></a>Regeln  
  
- **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene für die `Get` oder die `Set` Prozedur angeben, jedoch nicht für beide. Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft. Wenn die Eigenschaft beispielsweise als `Friend`deklariert ist, können Sie die `Set` Prozedur `Private`deklarieren, jedoch nicht `Public`.  
  
     Wenn Sie eine `WriteOnly`-Eigenschaft definieren, stellt die `Set` Prozedur die gesamte-Eigenschaft dar. Sie können für `Set`keine andere Zugriffsebene deklarieren, da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zurückgeben von einer Eigenschaften Prozedur.** Wenn die `Set` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung nach der Anweisung fortgesetzt, die den zu speichernden Wert bereitgestellt hat.  
  
     `Set`-Eigenschaften Prozeduren können entweder mithilfe der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder der [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)zurückgegeben werden.  
  
     Die Anweisungen `Exit Property` und `Return` führen zu einem sofortigen Beenden einer Eigenschaften Prozedur. Eine beliebige Anzahl von `Exit Property`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Property`-und `Return`-Anweisungen mischen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Set`-Anweisung verwendet, um den Wert einer Eigenschaft festzulegen.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Siehe auch

- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
