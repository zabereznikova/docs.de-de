---
title: Die Typargumente konnten nicht vom Delegaten abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 17b65a39082ddaf54aabf12ca9b95e49af80f5f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666305"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Die Typargumente konnten nicht vom Delegaten abgeleitet werden
Eine Zuweisungsanweisung verwendet `AddressOf` , um die Adresse einer generischen Prozedur zu einem Delegaten zuzuweisen, aber sie stellt keine Typargumente für die generische Prozedur bereit.  
  
 Wenn Sie einen generischen Typ aufrufen, geben Sie in der Regel für jeden Typparameter, der durch den generischen Typ definiert wird, ein Typargument an. Wenn Sie keine Typargumente angeben, versucht der Compiler, die an die Typparameter zu übergebenden Typen abzuleiten. Wenn der Kontext nicht genügend Informationen für den Compiler für die Ableitung der Typen bereitstellt, wird ein Fehler generiert.  
  
 **Fehler-ID:** BC36564  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie im `AddressOf` -Ausdruck die Typargumente für die generische Prozedur an.  
  
## <a name="see-also"></a>Siehe auch
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
- [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
