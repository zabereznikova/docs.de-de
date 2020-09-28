---
description: Kontextabhängiges value-Schlüsselwort – C#-Referenz
title: Kontextabhängiges value-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828915"
---
# <a name="value-c-reference"></a><span data-ttu-id="372ea-103">value (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="372ea-103">value (C# Reference)</span></span>

<span data-ttu-id="372ea-104">Das kontextabhängige Schlüsselwort `value` wird im `set`-Accessor in den Deklarationen [property](../../programming-guide/classes-and-structs/properties.md) und [indexer](../../programming-guide/indexers/index.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="372ea-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="372ea-105">Es ähnelt einem Eingabeparameter einer Methode.</span><span class="sxs-lookup"><span data-stu-id="372ea-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="372ea-106">Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft oder dem Indexer zuweisen möchte.</span><span class="sxs-lookup"><span data-stu-id="372ea-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="372ea-107">Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="372ea-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="372ea-108">Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="372ea-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="372ea-109">Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](../../programming-guide/classes-and-structs/properties.md) und [Indexern](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="372ea-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexers](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="372ea-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="372ea-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="372ea-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="372ea-111">See also</span></span>

- [<span data-ttu-id="372ea-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="372ea-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="372ea-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="372ea-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="372ea-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="372ea-114">C# Keywords</span></span>](index.md)
