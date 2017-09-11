---
title: get (C#-Referenz)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
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
ms.openlocfilehash: 88603864ae0a31a193cab211b8ce8061ec63c169
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="get-c-reference"></a><span data-ttu-id="548c3-102">get (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="548c3-102">get (C# Reference)</span></span>

<span data-ttu-id="548c3-103">Das Schlüsselwort `get` definiert eine *Accessor*methode in einer Eigenschaft oder einem Indexer, die den Eigenschaftswert oder das Indexer-Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="548c3-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="548c3-104">Weitere Informationen finden Sie unter [Properties (Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers (Indexer)](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="548c3-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="548c3-105">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="548c3-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="548c3-106">Im Beispiel wird ein privates Feld namens `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="548c3-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 <span data-ttu-id="548c3-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="548c3-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span></span>  
  
<span data-ttu-id="548c3-108">Der `get`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="548c3-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="548c3-109">Beginnend mit dem C# 7, können sie den `get`-Accessor als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="548c3-109">Starting with C# 7, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="548c3-110">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="548c3-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 <span data-ttu-id="548c3-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="548c3-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span></span>   
 
<span data-ttu-id="548c3-112">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="548c3-112">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="548c3-113">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="548c3-113">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 <span data-ttu-id="548c3-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="548c3-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="548c3-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="548c3-115">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="548c3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="548c3-116">See Also</span></span>  
 <span data-ttu-id="548c3-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="548c3-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="548c3-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="548c3-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="548c3-119">[C# Keywords (C#-Schlüsselwörter)](../../../csharp/language-reference/keywords/index.md) [Properties (Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/properties.md)</span><span class="sxs-lookup"><span data-stu-id="548c3-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md)</span></span>

