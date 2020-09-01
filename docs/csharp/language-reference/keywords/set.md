---
description: set-Schlüsselwort – C#-Referenz
title: set-Schlüsselwort – C#-Referenz
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: ff0c99e5d4d6271351783befd6650d9a77f39886
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136914"
---
# <a name="set-c-reference"></a><span data-ttu-id="63254-103">set (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="63254-103">set (C# Reference)</span></span>

<span data-ttu-id="63254-104">Das Schlüsselwort `set` definiert eine *Accessor*-Methode in einer Eigenschaft oder einem Indexer, die der Eigenschaft oder dem Indexer-Element einen Wert zuweist.</span><span class="sxs-lookup"><span data-stu-id="63254-104">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="63254-105">Weitere Informationen und Beispiele finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Automatisch implementierte Eigenschaften](../../programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="63254-105">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="63254-106">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="63254-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="63254-107">Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63254-107">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

<span data-ttu-id="63254-108">Der `set`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="63254-108">Often, the `set` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="63254-109">Ab C# 7.0 können Sie die `set`-Zugriffsmethode als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="63254-109">Starting with C# 7.0, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="63254-110">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="63254-110">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
<span data-ttu-id="63254-111">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="63254-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="63254-112">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="63254-112">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="63254-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="63254-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="63254-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63254-114">See also</span></span>

- [<span data-ttu-id="63254-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="63254-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="63254-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="63254-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="63254-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="63254-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="63254-118">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="63254-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
