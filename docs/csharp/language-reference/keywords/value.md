---
title: Kontextabhängiges value-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 34b192d17bd96b6b893c9f14f0d4a77274a32f78
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771744"
---
# <a name="value-c-reference"></a><span data-ttu-id="d350f-102">value (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d350f-102">value (C# Reference)</span></span>

<span data-ttu-id="d350f-103">Das kontextabhängige Schlüsselwort `value` wird im `set`-Accessor in den Deklarationen [property](../../programming-guide/classes-and-structs/properties.md) und [indexer](../../programming-guide/indexers/index.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="d350f-103">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="d350f-104">Es ähnelt einem Eingabeparameter einer Methode.</span><span class="sxs-lookup"><span data-stu-id="d350f-104">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="d350f-105">Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft oder dem Indexer zuweisen möchte.</span><span class="sxs-lookup"><span data-stu-id="d350f-105">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="d350f-106">Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d350f-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="d350f-107">Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d350f-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="d350f-108">Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](../../programming-guide/classes-and-structs/properties.md) und [Indexern](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d350f-108">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d350f-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d350f-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d350f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d350f-110">See also</span></span>

- [<span data-ttu-id="d350f-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d350f-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d350f-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d350f-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d350f-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d350f-113">C# Keywords</span></span>](index.md)
