---
description: get – C#-Referenz
title: get – C#-Referenz
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 7e13dc3ed6577717c64b4e36000a9e090f7b4751
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89139735"
---
# <a name="get-c-reference"></a><span data-ttu-id="b6fd6-103">get (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b6fd6-103">get (C# Reference)</span></span>

<span data-ttu-id="b6fd6-104">Das Schlüsselwort `get` definiert eine *Accessor* methode in einer Eigenschaft oder einem Indexer, die den Eigenschaftswert oder das Indexer-Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-104">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="b6fd6-105">Weitere Informationen finden Sie unter [Properties (Eigenschaften)](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers (Indexer)](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b6fd6-105">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="b6fd6-106">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="b6fd6-107">Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-107">It uses a private field named `_seconds` to back the property value.</span></span>  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="b6fd6-108">Der `get`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="b6fd6-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="b6fd6-109">Ab C# 7.0 können Sie die `get`-Zugriffsmethode als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-109">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="b6fd6-110">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

<span data-ttu-id="b6fd6-111">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="b6fd6-112">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="b6fd6-112">The following example implements `Hours` as an auto-implemented property.</span></span>
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b6fd6-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b6fd6-113">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6fd6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6fd6-114">See also</span></span>

- [<span data-ttu-id="b6fd6-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b6fd6-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b6fd6-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b6fd6-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b6fd6-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b6fd6-117">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b6fd6-118">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b6fd6-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
