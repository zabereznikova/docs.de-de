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
ms.openlocfilehash: b3524769567a56a87184bf916a3e5ccb1fd4fa1c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871758"
---
# <a name="set-statement-visual-basic"></a>Set-Anweisung (Visual Basic)

Deklariert eine- `Set` Eigenschaften Prozedur, mit der einer Eigenschaft ein Wert zugewiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Bestandteile  

 `attributelist`  
 Dies ist optional. Siehe [Attribut Liste](attribute-list.md).  
  
 `accessmodifier`  
 Optional für höchstens eine der `Get` -und- `Set` Anweisungen in dieser Eigenschaft. Dabei kann es sich um eine der folgenden Methoden handeln:  
  
- [Gebieten](../modifiers/protected.md)  
  
- [Friend](../modifiers/friend.md)  
  
- [Privat](../modifiers/private.md)  
  
- `Protected Friend`  
  
 Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Erforderlich. -Parameter, der den neuen Wert für die Eigenschaft enthält.  
  
 `datatype`  
 Erforderlich, wenn `Option Strict` ist `On` . Datentyp des `value` Parameters. Der angegebene Datentyp muss mit dem Datentyp der Eigenschaft übereinstimmen, in der diese `Set` Anweisung deklariert ist.  
  
 `statements`  
 Dies ist optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die- `Set` Eigenschaften Prozedur aufgerufen wird.  
  
 `End Set`  
 Erforderlich. Beendet die Definition der `Set` Eigenschaften Prozedur.  
  
## <a name="remarks"></a>Bemerkungen  

 Jede Eigenschaft muss über eine `Set` Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist gekennzeichnet `ReadOnly` . Die `Set` Prozedur wird verwendet, um den Wert der-Eigenschaft festzulegen.  
  
 Visual Basic automatisch die-Prozedur einer Eigenschaft aufruft `Set` , wenn eine Zuweisungsanweisung einen Wert bereitstellt, der in der-Eigenschaft gespeichert werden soll.  
  
 Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften Zuweisungen. Wenn Sie keinen Parameter für angeben `Set` , verwendet die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) einen impliziten Parameter mit dem Namen `value` . Der-Parameter enthält den Wert, der der-Eigenschaft zugewiesen werden soll. In der Regel speichern Sie diesen Wert in einer privaten lokalen Variable und geben ihn immer dann zurück, wenn die `Get` Prozedur aufgerufen wird.  
  
 Der Text der Eigenschafts Deklaration darf nur die- `Get` und- `Set` Prozeduren der Eigenschaft zwischen der- [Eigenschafts Anweisung](property-statement.md) und der- `End Property` Anweisung enthalten. Es kann nichts anderes als diese Prozeduren speichern. Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden. Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen. Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist. Sie müssen eine `Set` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.  
  
 Die `Set` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der- `Set` Anweisung.  
  
## <a name="rules"></a>Regeln  
  
- **Gemischte Zugriffsebenen.** Wenn Sie eine Lese-/Schreibeigenschaft definieren, können Sie optional eine andere Zugriffsebene für die- `Get` oder die- `Set` Prozedur angeben, aber nicht beides. Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft. Wenn beispielsweise die-Eigenschaft deklariert wird `Friend` , können Sie die Prozedur deklarieren `Set` `Private` , jedoch nicht `Public` .  
  
     Wenn Sie eine Eigenschaft definieren `WriteOnly` , stellt die `Set` Prozedur die gesamte Eigenschaft dar. Sie können keine andere Zugriffsebene für deklarieren `Set` , da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zurückgeben von einer Eigenschaften Prozedur.** Wenn die `Set` Prozedur an den aufrufenden Code zurückkehrt, wird die Ausführung nach der Anweisung fortgesetzt, die den zu speichernden Wert bereitgestellt hat.  
  
     `Set` Eigenschaften Prozeduren können entweder mithilfe der [Return-Anweisung](return-statement.md) oder der Exit- [Anweisung](exit-statement.md)zurückgegeben werden.  
  
     Die `Exit Property` -und- `Return` Anweisungen führen zu einem sofortigen Beenden einer Eigenschaften Prozedur. Eine beliebige Anzahl von `Exit Property` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Property` -und- `Return` Anweisungen  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die- `Set` Anweisung verwendet, um den Wert einer Eigenschaft festzulegen.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Get-Anweisung](get-statement.md)
- [Property Statement](property-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Eigenschaftenprozeduren](../../programming-guide/language-features/procedures/property-procedures.md)
