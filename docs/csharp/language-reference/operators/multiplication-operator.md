---
title: '* Operator (C#-Referenz)'
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 873cc1dc0d81425117f1784353acf08b35158133
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225359"
---
# <a name="-operator-c-reference"></a>Operator * (C#-Referenz)
Der Multiplikationsoperator (`*`) berechnet das Produkt seiner Operanden. Alle numerischen Typen besitzen vordefinierte Multiplikationsoperatoren.  

`*` dient auch als Dereferenzierungsoperator, der das Lesen und Schreiben in einen Zeiger ermöglicht.
  
## <a name="remarks"></a>Hinweise  
 Der `*`-Operator wird auch verwendet, um Zeigertypen zu deklarieren und Zeiger zu dereferenzieren. Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, gekennzeichnet durch die Verwendung des [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselworts und erfordert die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Die englischen Begriffe „dereference operator“ und „indirection operator“ bezeichnen beide den Dereferenzierungsoperator.  
  
 Benutzerdefinierte Typen können den binären `*`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)). Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
