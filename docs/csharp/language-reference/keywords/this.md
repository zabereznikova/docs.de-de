---
title: this-Schlüsselwort – C#-Referenz
description: Schlüsselwort „this“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715110"
---
# <a name="this-c-reference"></a><span data-ttu-id="4d598-103">this (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4d598-103">this (C# Reference)</span></span>

<span data-ttu-id="4d598-104">Das Schlüsselwort `this` verweist auf die aktuelle Instanz der Klasse und wird auch als Modifizierer des ersten Parameters einer Erweiterungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d598-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="4d598-105">Dieser Artikel behandelt die Verwendung von `this` mit Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="4d598-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="4d598-106">Weitere Informationen zu seiner Verwendung in Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4d598-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="4d598-107">Häufige Verwendungen von `this` sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4d598-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="4d598-108">Zum Qualifizieren von Membern, die durch ähnliche Namen ausgeblendet werden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="4d598-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="4d598-109">Zum Übergeben eines Objekts als ein Parameter an eine andere Methode, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="4d598-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="4d598-110">Zum Deklarieren von Indexern, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="4d598-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="4d598-111">Statische Memberfunktionen haben keinen `this`-Zeiger, da sie auf Klassenebene und nicht als Teil eines Objekts existieren.</span><span class="sxs-lookup"><span data-stu-id="4d598-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="4d598-112">Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4d598-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="4d598-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d598-113">Example</span></span>

<span data-ttu-id="4d598-114">In diesem Beispiel wird `this` verwendet, um die `Employee`-Klassenmember `name` und `alias` zu qualifizieren, die von ähnlichen Namen ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d598-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="4d598-115">Er wird auch verwendet, um ein Objekt an die Methode `CalcTax` zu übergeben, die zu einer anderen Klasse gehört.</span><span class="sxs-lookup"><span data-stu-id="4d598-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="4d598-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d598-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4d598-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d598-117">See also</span></span>

- [<span data-ttu-id="4d598-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4d598-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4d598-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4d598-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4d598-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4d598-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4d598-121">base</span><span class="sxs-lookup"><span data-stu-id="4d598-121">base</span></span>](base.md)
- [<span data-ttu-id="4d598-122">Methoden</span><span class="sxs-lookup"><span data-stu-id="4d598-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
