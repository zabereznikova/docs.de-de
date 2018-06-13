---
title: C#-Enumerationen – Überblick über C#
description: Hier lernen Sie Enumerationen kennen, separate benannte Konstanten in C#.
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353353"
---
# <a name="enums"></a><span data-ttu-id="40f5c-103">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="40f5c-103">Enums</span></span>

<span data-ttu-id="40f5c-104">Ein ***Enumerationstyp*** ist ein eindeutiger Werttyp mit einem Satz benannter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="40f5c-104">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="40f5c-105">Sie definieren die Enumerationen, wenn Sie einen Typ definieren müssen, der einen Satz von diskreten Werten haben kann.</span><span class="sxs-lookup"><span data-stu-id="40f5c-105">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="40f5c-106">Die Enumerationen verwenden einen der ganzzahligen Werttypen als ihren zugrunde liegenden Speicher.</span><span class="sxs-lookup"><span data-stu-id="40f5c-106">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="40f5c-107">Sie liefern die Bedeutung der diskreten Werte.</span><span class="sxs-lookup"><span data-stu-id="40f5c-107">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="40f5c-108">Das folgende Beispiel deklariert und verwendet einen `enum`-Typ mit dem Namen `Color` mit drei konstanten Werten, `Red`, `Green` und `Blue`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-108">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="40f5c-109">Jeder `enum`-Typ verfügt über einen entsprechenden ganzzahligen Typ, der als der ***zugrunde liegende Typ*** des `enum`-Typs bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="40f5c-109">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="40f5c-110">Ein `enum`-Typ, der nicht explizit einen zugrunde liegenden Typ deklariert, verfügt über einen zugrunde liegenden `int`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40f5c-110">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="40f5c-111">Das Speicherformat eines `enum`-Typs und der Bereich der möglichen Werte werden durch den ihm zugrunde liegenden Typ bestimmt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-111">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="40f5c-112">Der Satz von Werten, die ein `enum`-Typ ausführen kann, ist nicht durch seine `enum`-Member beschränkt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-112">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="40f5c-113">Insbesondere jeder Wert des zugrunde liegenden Typs einer `enum` kann in den `enum`-Typ umgewandelt werden und ist ein eindeutiger gültiger Wert dieses `enum`-Typs.</span><span class="sxs-lookup"><span data-stu-id="40f5c-113">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="40f5c-114">Das folgende Beispiel deklariert einen `enum`-Typ mit dem Namen `Alignment` und einem zugrunde liegenden Typ `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-114">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="40f5c-115">Wie im vorherigen Beispiel gezeigt, kann eine `enum`-Memberdeklaration einen konstanten Ausdruck beinhalten, der den Wert des Members angibt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-115">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="40f5c-116">Der konstante Wert für jeden `enum`-Member muss im Bereich des zugrunde liegenden Typs der `enum` sein.</span><span class="sxs-lookup"><span data-stu-id="40f5c-116">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="40f5c-117">Wenn eine `enum`-Memberdeklaration nicht explizit einen Wert angibt, erhält der Member den Wert 0 (null) (falls dies der erste Member im `enum`-Typ ist) oder den Wert des textlich vorausgehenden `enum`-Members plus eins.</span><span class="sxs-lookup"><span data-stu-id="40f5c-117">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="40f5c-118">`Enum`-Werte können mit Typumwandlungen in ganzzahlige Werte und umgekehrt konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="40f5c-118">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="40f5c-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40f5c-119">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="40f5c-120">Der Standardwert eines beliebigen `enum`-Typs ist der ganzzahlige Wert 0 (null) konvertiert in den `enum`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40f5c-120">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="40f5c-121">In Fällen, in denen Variablen automatisch auf einen Standardwert initialisiert werden, ist dies der Wert der Variablen von `enum`-Typen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-121">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="40f5c-122">Damit der Standardwert eines `enum`-Typs leicht verfügbar ist, wird das Literal `0` implizit in einen `enum`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="40f5c-122">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="40f5c-123">Daher ist Folgendes zugelassen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-123">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
<span data-ttu-id="40f5c-124">[Zurück](interfaces.md)
[Weiter](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="40f5c-124">[Previous](interfaces.md)
[Next](delegates.md)</span></span>
