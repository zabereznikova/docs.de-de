---
title: interface (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 126e674a2c56f04f54f35a011c24ebf0f713ee8d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="interface-c-reference"></a>interface (C#-Referenz)
Eine Schnittstelle enthält nur die Signaturen von [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Ereignissen](../../../csharp/programming-guide/events/index.md) oder [Indexern](../../../csharp/programming-guide/indexers/index.md). Eine Klasse oder eine Struktur, die die Schnittstelle implementiert, muss die Member der Schnittstelle implementieren, die in der Schnittstellendefinition angegeben werden. Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.  
  
 Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein und Signaturen der folgenden Member enthalten:  
  
-   [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Indexer](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Ereignisse](../../../csharp/language-reference/keywords/event.md)  
  
 Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben.  
  
 Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.  
  
 Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren. Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz.  
  
 Weitere Details und Codebeispiele zur expliziten Schnittstellenimplementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung. In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung. Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.  
  
 [!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md)   
 [class](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)

