---
title: AddressOf-Operator
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: edce7d4a2268bd311045ea4972672fe8fd2600ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874893"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf-Operator (Visual Basic)

Erstellt eine Delegatinstanz, die auf die jeweilige Prozedur verweist.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Bestandteile  

 `procedurename`  
 Erforderlich. Gibt die Prozedur an, auf die durch den neu erstellten Delegaten verwiesen werden soll.  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `AddressOf` Operator erstellt einen Delegaten, der auf die durch angegebene untergeordnete or-Funktion verweist `procedurename` . Wenn die angegebene Prozedur eine Instanzmethode ist, verweist der Delegat sowohl auf die-Instanz als auch auf die-Methode. Wenn der Delegat aufgerufen wird, wird die angegebene Methode der angegebenen-Instanz aufgerufen.  
  
 Der `AddressOf` Operator kann als Operand eines Delegatkonstruktors oder in einem Kontext verwendet werden, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird der- `AddressOf` Operator verwendet, um einen Delegaten zur Behandlung des- `Click` Ereignisses einer Schaltfläche festzulegen.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `AddressOf` Operator verwendet, um die Startup-Funktion für einen Thread festzulegen.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Declare Statement](../statements/declare-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Sub-Anweisung](../statements/sub-statement.md)
- [Delegaten](../../programming-guide/language-features/delegates/index.md)
