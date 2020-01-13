---
title: get – C#-Referenz
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: d6c0452a7890a6ade480054115c1383199a3f91c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713490"
---
# <a name="get-c-reference"></a><span data-ttu-id="598e6-102">get (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="598e6-102">get (C# Reference)</span></span>

<span data-ttu-id="598e6-103">Das Schlüsselwort `get` definiert eine *Accessor*methode in einer Eigenschaft oder einem Indexer, die den Eigenschaftswert oder das Indexer-Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="598e6-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="598e6-104">Weitere Informationen finden Sie unter [Properties (Eigenschaften)](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers (Indexer)](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="598e6-104">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="598e6-105">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="598e6-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="598e6-106">Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="598e6-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="598e6-107">Der `get`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="598e6-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="598e6-108">Ab C# 7.0 können Sie die `get`-Zugriffsmethode als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="598e6-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="598e6-109">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="598e6-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
<span data-ttu-id="598e6-110">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="598e6-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="598e6-111">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="598e6-111">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="598e6-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="598e6-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="598e6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="598e6-113">See also</span></span>

- [<span data-ttu-id="598e6-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="598e6-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="598e6-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="598e6-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="598e6-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="598e6-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="598e6-117">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="598e6-117">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
