---
title: "C#-Enumerationen – Überblick über C#"
description: Hier lernen Sie Enumerationen kennen, separate benannte Konstanten in C#.
keywords: .NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 77d315dd87d9cab32605de415674d146eb9115fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="enums"></a><span data-ttu-id="95316-104">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="95316-104">Enums</span></span>

<span data-ttu-id="95316-105">Ein ***Enumerationstyp*** ist ein eindeutiger Werttyp mit einem Satz benannter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="95316-105">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="95316-106">Sie definieren die Enumerationen, wenn Sie einen Typ definieren müssen, der einen Satz von diskreten Werten haben kann.</span><span class="sxs-lookup"><span data-stu-id="95316-106">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="95316-107">Die Enumerationen verwenden einen der ganzzahligen Werttypen als ihren zugrunde liegenden Speicher.</span><span class="sxs-lookup"><span data-stu-id="95316-107">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="95316-108">Sie liefern die Bedeutung der diskreten Werte.</span><span class="sxs-lookup"><span data-stu-id="95316-108">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="95316-109">Das folgende Beispiel deklariert und verwendet einen `enum`-Typ mit dem Namen `Color` mit drei konstanten Werten, `Red`, `Green` und `Blue`.</span><span class="sxs-lookup"><span data-stu-id="95316-109">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="95316-110">Jeder `enum`-Typ verfügt über einen entsprechenden ganzzahligen Typ, der als der ***zugrunde liegende Typ*** des `enum`-Typs bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="95316-110">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="95316-111">Ein `enum`-Typ, der nicht explizit einen zugrunde liegenden Typ deklariert, verfügt über einen zugrunde liegenden `int`-Typ.</span><span class="sxs-lookup"><span data-stu-id="95316-111">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="95316-112">Das Speicherformat eines `enum`-Typs und der Bereich der möglichen Werte werden durch den ihm zugrunde liegenden Typ bestimmt.</span><span class="sxs-lookup"><span data-stu-id="95316-112">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="95316-113">Der Satz von Werten, die ein `enum`-Typ ausführen kann, ist nicht durch seine `enum`-Member beschränkt.</span><span class="sxs-lookup"><span data-stu-id="95316-113">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="95316-114">Insbesondere jeder Wert des zugrunde liegenden Typs einer `enum` kann in den `enum`-Typ umgewandelt werden und ist ein eindeutiger gültiger Wert dieses `enum`-Typs.</span><span class="sxs-lookup"><span data-stu-id="95316-114">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="95316-115">Das folgende Beispiel deklariert einen `enum`-Typ mit dem Namen `Alignment` und einem zugrunde liegenden Typ `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="95316-115">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="95316-116">Wie im vorherigen Beispiel gezeigt, kann eine `enum`-Memberdeklaration einen konstanten Ausdruck beinhalten, der den Wert des Members angibt.</span><span class="sxs-lookup"><span data-stu-id="95316-116">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="95316-117">Der konstante Wert für jeden `enum`-Member muss im Bereich des zugrunde liegenden Typs der `enum` sein.</span><span class="sxs-lookup"><span data-stu-id="95316-117">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="95316-118">Wenn eine `enum`-Memberdeklaration nicht explizit einen Wert angibt, erhält der Member den Wert 0 (null) (falls dies der erste Member im `enum`-Typ ist) oder den Wert des textlich vorausgehenden `enum`-Members plus eins.</span><span class="sxs-lookup"><span data-stu-id="95316-118">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="95316-119">`Enum`-Werte können mit Typumwandlungen in ganzzahlige Werte und umgekehrt konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="95316-119">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="95316-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95316-120">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="95316-121">Der Standardwert eines beliebigen `enum`-Typs ist der ganzzahlige Wert 0 (null) konvertiert in den `enum`-Typ.</span><span class="sxs-lookup"><span data-stu-id="95316-121">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="95316-122">In Fällen, in denen Variablen automatisch auf einen Standardwert initialisiert werden, ist dies der Wert der Variablen von `enum`-Typen.</span><span class="sxs-lookup"><span data-stu-id="95316-122">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="95316-123">Damit der Standardwert eines `enum`-Typs leicht verfügbar ist, wird das Literal `0` implizit in einen `enum`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="95316-123">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="95316-124">Daher ist Folgendes zugelassen.</span><span class="sxs-lookup"><span data-stu-id="95316-124">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
<span data-ttu-id="95316-125">[Zurück](interfaces.md)
[Weiter](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="95316-125">[Previous](interfaces.md)
[Next](delegates.md)</span></span>
