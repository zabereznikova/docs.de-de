---
title: Enumerationstypen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969767"
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="0e695-102">Enumerationstypen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0e695-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="0e695-103">Ein Enumerationstyp (auch Enumeration oder enum genannt) bietet eine effiziente Möglichkeit zum Definieren von benannten ganzzahligen Konstanten, die einer Variablen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="0e695-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="0e695-104">Nehmen wir beispielsweise an, Sie müssen eine Variable definieren, deren Wert einen Tag der Woche darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e695-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="0e695-105">Es gibt nur sieben sinnvolle Werte, die diese Variable speichern kann.</span><span class="sxs-lookup"><span data-stu-id="0e695-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="0e695-106">Sie können einen Enumerationstyp verwenden, der mithilfe des [enum](../language-reference/keywords/enum.md)-Schlüsselworts deklariert wurde, um diese Werte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0e695-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="0e695-107">Standardmäßig ist [int](../language-reference/builtin-types/integral-numeric-types.md) der zugrunde liegende Typ jedes Elements in enum. Sie können mithilfe eines Doppelpunktes einen anderen ganzzahligen numerischen Typ angeben, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e695-107">By default the underlying type of each element in the enum is [int](../language-reference/builtin-types/integral-numeric-types.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="0e695-108">Eine vollständige Liste der möglichen Typen finden Sie unter [enum (C#-Referenz)](../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="0e695-108">For a full list of possible types, see [enum (C# Reference)](../language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="0e695-109">Sie können die zugrunde liegenden numerischen Werte durch Umwandeln in den zugrunde liegenden Typ, wie im folgenden Beispiel gezeigt, überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e695-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="0e695-110">Im Folgenden werden die Vorteile der Verwendung eines enum anstelle eines numerischen Typs gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0e695-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="0e695-111">Sie geben für Clientcode eindeutig die Werte an, die für die Variable gültig sind.</span><span class="sxs-lookup"><span data-stu-id="0e695-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="0e695-112">In Visual Studio listet IntelliSense die definierten Werte auf.</span><span class="sxs-lookup"><span data-stu-id="0e695-112">In Visual Studio, IntelliSense lists the defined values.</span></span>

<span data-ttu-id="0e695-113">Wenn Sie keine Werte für die Elemente in der Enumeratorliste angeben, werden die Werte automatisch um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="0e695-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="0e695-114">Im vorherigen Beispiel hat `Day.Sunday` den Wert 0, `Day.Monday` hat den Wert 1 und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0e695-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="0e695-115">Beim Erstellen eines neuen `Day`-Objekt, wird es den Standardwert `Day.Sunday` (0) aufweisen, wenn Sie nicht explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0e695-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="0e695-116">Wenn Sie ein enum erstellen, wählen Sie den logischen Standardwert aus und weisen Sie ihm einen Wert von Null zu.</span><span class="sxs-lookup"><span data-stu-id="0e695-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="0e695-117">Dadurch werden alle Enumerationen über diesen Standardwert verfügen, wenn sie nicht explizit einen Wert zugewiesen bekommen, wenn sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e695-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="0e695-118">Wenn die Variable `meetingDay` vom Typ `Day` ist, dann können Sie (ohne eine explizite Umwandlung) für sie nur einen der durch `Day` definierten Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0e695-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="0e695-119">Und wenn sich der Sitzungstag ändert, können Sie einen neuen Wert von `Day` auf `meetingDay` zuweisen:</span><span class="sxs-lookup"><span data-stu-id="0e695-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="0e695-120">Es ist möglich, einen beliebigen ganzzahligen Wert an `meetingDay` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0e695-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="0e695-121">Diese Codezeile ergibt z.B. keinen Fehler: `meetingDay = (Day) 42`.</span><span class="sxs-lookup"><span data-stu-id="0e695-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="0e695-122">Allerdings sollten Sie dies nicht tun, da implizit erwartet wird, dass eine Enumerationensvariable nur einen der von enum definierten Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="0e695-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="0e695-123">Einen beliebigen Wert einer Variablen eines Enumerationstyps zuzuweisen bedeutet, ein hohes Fehlerrisiko einzuführen.</span><span class="sxs-lookup"><span data-stu-id="0e695-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="0e695-124">Sie können den Elementen in der Enumeratorliste eines Enumerationstyps Werte zuweisen, und Sie können auch berechnete Werte verwenden:</span><span class="sxs-lookup"><span data-stu-id="0e695-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="0e695-125">Enumerationstypen als Bitflags</span><span class="sxs-lookup"><span data-stu-id="0e695-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="0e695-126">Sie können einen Enumerationstyp zum Definieren von Bitflags verwenden. Dadurch kann eine Instanz des Enumerationstyps eine beliebige Kombination der Werte speichern, die in der Enumeratorliste definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0e695-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="0e695-127">(Natürlich können einige Kombinationen nicht sinnvoll oder in Ihrem Programmcode nicht zulässig sein.)</span><span class="sxs-lookup"><span data-stu-id="0e695-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="0e695-128">Sie erstellen ein Bitflags-Enum durch Anwenden des Attributs <xref:System.FlagsAttribute?displayProperty=nameWithType> und definieren die Werte entsprechend, damit die bitweisen Operationen `AND`, `OR`, `NOT` und `XOR` ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="0e695-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="0e695-129">In einem Bitflag-Enum ist eine benannte Konstante mit dem Wert Null enthalten, das bedeutet, dass „keine Flags festgelegt sind“.</span><span class="sxs-lookup"><span data-stu-id="0e695-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="0e695-130">Geben Sie einem Flag keinen Wert Null, wenn es nicht bedeutet, dass „keine Flags festgelegt sind“.</span><span class="sxs-lookup"><span data-stu-id="0e695-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="0e695-131">Im folgenden Beispiel ist eine andere Version der `Day`-Enum mit dem Namen `Days` definiert.</span><span class="sxs-lookup"><span data-stu-id="0e695-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="0e695-132">`Days` verfügt über das `Flags`-Attribut, und jedem Wert wird die nächste höhere Potenz von 2 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0e695-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="0e695-133">Dies ermöglicht Ihnen die Erstellung einer `Days`-Variable, deren Wert `Days.Tuesday | Days.Thursday` ist.</span><span class="sxs-lookup"><span data-stu-id="0e695-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="0e695-134">Um ein Flag für einen enum festzulegen, verwenden Sie den bitweisen `OR` Operator, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0e695-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="0e695-135">Verwenden Sie einen bitweisen `AND`-Vorgang, wie im folgenden Beispiel gezeigt, um zu bestimmen, ob ein bestimmtes Flag festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="0e695-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="0e695-136">Weitere Informationen zu den notwendigen Überlegungen beim Definieren von Enumerationstypen mit dem <xref:System.FlagsAttribute?displayProperty=nameWithType>-Attribut finden Sie unter <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e695-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="0e695-137">Verwenden der Methoden System.Enum zum Ermitteln und Bearbeiten der Enumerationswerte</span><span class="sxs-lookup"><span data-stu-id="0e695-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="0e695-138">Alle Enumerationen sind Instanzen des Typs <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e695-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="0e695-139">Sie können keine neuen Klassen von <xref:System.Enum?displayProperty=nameWithType> ableiten, aber Sie können die zugehörigen Methoden verwenden, um Informationen zu ermitteln und Werte in einer enum-Instanz zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e695-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="0e695-140">Weitere Informationen finden Sie unter <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e695-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0e695-141">Sie können auch mithilfe einer Erweiterungsmethode eine neue Methode für ein enum erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e695-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="0e695-142">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0e695-142">For more information, see [How to create a new method for an enumeration](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e695-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e695-143">See also</span></span>

- <xref:System.Enum?displayProperty=nameWithType>
- [<span data-ttu-id="0e695-144">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0e695-144">C# Programming Guide</span></span>](./index.md)
- [<span data-ttu-id="0e695-145">enum</span><span class="sxs-lookup"><span data-stu-id="0e695-145">enum</span></span>](../language-reference/keywords/enum.md)
