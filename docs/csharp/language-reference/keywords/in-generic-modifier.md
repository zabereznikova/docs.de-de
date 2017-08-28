---
title: in (generischer Modifizierer) (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: de-de
ms.lasthandoff: 08/11/2017

---
# <a name="in-generic-modifier-c-reference"></a>in (generischer Modifizierer) (C#-Referenz)
Das Schlüsselwort `in` gibt für generische Typparameter an, dass der Typparameter kontravariant ist. Sie können das Schlüsselwort `in` in generischen Schnittstellen und Delegaten verwenden.  
  
 Kontravarianz ermöglicht Ihnen die Verwendung eines weniger stark abgeleiteten Typs als der durch den generischen Parameter angegebene. Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert. Kovarianz und Kontravarianz in generischen Typparametern werden für Verweistypen unterstützt, aber nicht für Werttypen.  
  
 Ein Typ kann als kontravariant in einer generischen Schnittstelle oder einem generischen Delegaten deklariert werden, wenn er nur als Typ eines Methodenarguments und nicht als Methodenrückgabetyp verwendet wird. Die Parameter `Ref` und `out` dürfen nicht variant sein.  
  
 Mit einer Schnittstelle, die einen kontravarianten Typparameter hat, kann ihre Methode mehr abgeleitete Typen, als durch den Typparameter der Schnittstelle angegeben, akzeptieren. Da z.B. in .NET Framework 4 Typ T in der Schnittstelle <xref:System.Collections.Generic.IComparer%601> kontravariant ist, können Sie ein Objekt des `IComparer(Of Person)`-Typs an ein Objekt des `IComparer(Of Employee)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden, wenn `Employee` von `Person` erbt.  
  
 Ein kontravarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem weniger stark abgeleiteten generischen Typparameter.  
  
 Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine kontravariante generische Schnittstelle deklarieren, erweitern und implementieren können. Es wird auch gezeigt, wie Sie die implizite Konvertierung für Klassen verwenden können, die eine diese Schnittstelle implementieren können.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren, instanziieren und aufrufen. Es zeigt außerdem, wie Sie einen Delegattyp implizit konvertieren können.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)

