---
title: '&lt;&lt;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239172"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;=-Operator (C#-Referenz)
Der Linksschiebezuweisungs-Operator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck der Form  
  
```csharp  
x <<= y  
```  
  
 wird als ausgewertet,  
  
```csharp  
x = x << y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator <<](../../../csharp/language-reference/operators/left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.  
  
 Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) überladen (weitere Informationen unter [Operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
