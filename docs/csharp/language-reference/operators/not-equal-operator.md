---
title: Operator != (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: e974ffb1b25944e24fca23864dc7e932ec1876d5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46710734"
---
# <a name="-operator-c-reference"></a>Operator != (C#-Referenz)
Der Ungleichheitsoperator (`!=`) gibt FALSE zurück, wenn die Operanden gleich sind; andernfalls TRUE. Vergleichsoperatoren sind für alle Typen, einschließlich Zeichenfolgen und Objekte vordefiniert. Benutzerdefinierte Typen können den Operator `!=` überladen.  
  
## <a name="remarks"></a>Hinweise  
 Für vordefinierte Werttypen gibt der Ungleichheitsoperator (`!=`) TRUE zurück, wenn die Werte der Operanden verschieden sind; andernfalls FALSE. Für andere Verweistypen als `string`, `!=` wird TRUE zurückgegeben, wenn beide Operanden auf unterschiedliche Objekte verweisen. Für den `string`-Typ vergleicht `!=` die Werte der Zeichenfolgen.  
  
 Benutzerdefinierte Werttypen können den Operator `!=` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)). Dies können auch benutzerdefinierte Verweistypen, obwohl `!=` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält. Wenn `!=` überladen ist, muss [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) auch überladen werden. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
