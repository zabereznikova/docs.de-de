---
title: set (C#-Referenz)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- set
- set_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
caps.latest.revision: 14
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
ms.openlocfilehash: de10e3978d768aab34efa675fe00cfd059ff55df
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="set-c-reference"></a><span data-ttu-id="35aea-102">set (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="35aea-102">set (C# Reference)</span></span>
<span data-ttu-id="35aea-103">Das Schlüsselwort `set` definiert eine *Accessor*-Methode in einer Eigenschaft oder einem Indexer, die der Eigenschaft oder dem Indexer-Element einen Wert zuweist.</span><span class="sxs-lookup"><span data-stu-id="35aea-103">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="35aea-104">Weitere Informationen und Beispiele finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="35aea-104">For more information and examples, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="35aea-105">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="35aea-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="35aea-106">Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="35aea-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 <span data-ttu-id="35aea-107">[!code-cs[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="35aea-107">[!code-cs[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span></span>  

<span data-ttu-id="35aea-108">Der `set`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="35aea-108">Often, the `set` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="35aea-109">Ab C# 7 können sie den `set`-Accessor als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="35aea-109">Starting with C# 7, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="35aea-110">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="35aea-110">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

 <span data-ttu-id="35aea-111">[!code-cs[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="35aea-111">[!code-cs[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span></span>   
    
<span data-ttu-id="35aea-112">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="35aea-112">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="35aea-113">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="35aea-113">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 <span data-ttu-id="35aea-114">[!code-cs[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="35aea-114">[!code-cs[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span></span>  
    
## <a name="c-language-specification"></a><span data-ttu-id="35aea-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="35aea-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35aea-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35aea-116">See Also</span></span>  
 <span data-ttu-id="35aea-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="35aea-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="35aea-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="35aea-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="35aea-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="35aea-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="35aea-120">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="35aea-120">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

