---
title: set-Schlüsselwort – C#-Referenz
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: cdd84c824cc4dc93f4433f07e9978d22cba3f245
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795065"
---
# <a name="set-c-reference"></a><span data-ttu-id="2d55a-102">set (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2d55a-102">set (C# Reference)</span></span>

<span data-ttu-id="2d55a-103">Das Schlüsselwort `set` definiert eine *Accessor*-Methode in einer Eigenschaft oder einem Indexer, die der Eigenschaft oder dem Indexer-Element einen Wert zuweist.</span><span class="sxs-lookup"><span data-stu-id="2d55a-103">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="2d55a-104">Weitere Informationen und Beispiele finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Automatisch implementierte Eigenschaften](../../programming-guide/classes-and-structs/auto-implemented-properties.md) und [Indexers](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d55a-104">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="2d55a-105">Im folgenden Beispiel werden ein `get`- und ein `set`-Accessor für eine Eigenschaft namens `Seconds` definiert.</span><span class="sxs-lookup"><span data-stu-id="2d55a-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="2d55a-106">Im Beispiel wird ein privates Feld mit dem Namen `_seconds` verwendet, um den Eigenschaftswert zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2d55a-106">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

<span data-ttu-id="2d55a-107">Der `set`-Accessor besteht häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="2d55a-107">Often, the `set` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="2d55a-108">Ab C# 7.0 können Sie die `set`-Zugriffsmethode als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="2d55a-108">Starting with C# 7.0, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="2d55a-109">Im folgenden Beispiel wird sowohl der `get`- als auch der `set`-Accessor als Ausdruckskörpermember implementiert.</span><span class="sxs-lookup"><span data-stu-id="2d55a-109">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
<span data-ttu-id="2d55a-110">In einfachen Fällen, in denen der `get`- und der `set`-Accessor einer Eigenschaft nichts anderes durchführen als das Festlegen oder Abrufen eines Wertes in einem privaten Unterstützungsfeld, können Sie die Vorteile der Unterstützung von automatisch implementierten Eigenschaften durch einen C#-Compiler nutzen.</span><span class="sxs-lookup"><span data-stu-id="2d55a-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="2d55a-111">Im folgenden Beispiel wird `Hours` als automatisch implementierte Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2d55a-111">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="2d55a-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2d55a-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2d55a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d55a-113">See also</span></span>

- [<span data-ttu-id="2d55a-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2d55a-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2d55a-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2d55a-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2d55a-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2d55a-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2d55a-117">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d55a-117">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
