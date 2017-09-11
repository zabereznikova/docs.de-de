---
title: Enumerationstypen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="6e900-102">Enumerationstypen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6e900-102">Enumeration Types (C# Programming Guide)</span></span>
<span data-ttu-id="6e900-103">Ein Enumerationstyp (auch Enumeration oder enum genannt) bietet eine effiziente Möglichkeit zum Definieren von benannten ganzzahligen Konstanten, die einer Variablen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="6e900-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="6e900-104">Nehmen wir beispielsweise an, Sie müssen eine Variable definieren, deren Wert einen Tag der Woche darstellt.</span><span class="sxs-lookup"><span data-stu-id="6e900-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="6e900-105">Es gibt nur sieben sinnvolle Werte, die diese Variable speichern kann.</span><span class="sxs-lookup"><span data-stu-id="6e900-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="6e900-106">Sie können einen Enumerationstyp verwenden, der mithilfe des [enum](../../csharp/language-reference/keywords/enum.md)-Schlüsselworts deklariert wurde, um diese Werte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6e900-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>  
  
 <span data-ttu-id="6e900-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span></span>  
  
 <span data-ttu-id="6e900-108">Standardmäßig ist [int](../../csharp/language-reference/keywords/int.md) der zugrunde liegende Typ jedes Elements in enum.</span><span class="sxs-lookup"><span data-stu-id="6e900-108">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="6e900-109">Sie können mithilfe eines Doppelpunktes einen anderen ganzzahligen numerischen Typ angeben, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e900-109">You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="6e900-110">Eine vollständige Liste der möglichen Typen finden Sie unter [enum (C#-Referenz)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="6e900-110">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="6e900-111">Sie können die zugrunde liegenden numerischen Werte durch Umwandeln in den zugrunde liegenden Typ, wie im folgenden Beispiel gezeigt, überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6e900-111">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 <span data-ttu-id="6e900-112">Im Folgenden werden die Vorteile der Verwendung eines enum anstelle eines numerischen Typs gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e900-112">The following are advantages of using an enum instead of a numeric type:</span></span>  
  
-   <span data-ttu-id="6e900-113">Sie geben für Clientcode eindeutig die Werte an, die für die Variable gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6e900-113">You clearly specify for client code which values are valid for the variable.</span></span>  
  
-   <span data-ttu-id="6e900-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] listet IntelliSense die definierten Werte auf.</span><span class="sxs-lookup"><span data-stu-id="6e900-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>  
  
 <span data-ttu-id="6e900-115">Wenn Sie keine Werte für die Elemente in der Enumeratorliste angeben, werden die Werte automatisch um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="6e900-115">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="6e900-116">Im vorherigen Beispiel hat `Days.Sunday` den Wert 0, `Days.Monday` hat den Wert 1 und so weiter.</span><span class="sxs-lookup"><span data-stu-id="6e900-116">In the previous example, `Days.Sunday` has a value of 0, `Days.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="6e900-117">Beim Erstellen eines neuen `Days`-Objekt, wird es den Standardwert `Days.Sunday` (0) aufweisen, wenn Sie nicht explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e900-117">When you create a new `Days` object, it will have a default value of `Days.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="6e900-118">Wenn Sie ein enum erstellen, wählen Sie den logischen Standardwert aus und weisen Sie ihm einen Wert von Null zu.</span><span class="sxs-lookup"><span data-stu-id="6e900-118">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="6e900-119">Dadurch werden alle Enumerationen über diesen Standardwert verfügen, wenn sie nicht explizit einen Wert zugewiesen bekommen, wenn sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6e900-119">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>  
  
 <span data-ttu-id="6e900-120">Wenn die Variable `meetingDay` vom Typ `Days` ist, dann können Sie (ohne eine explizite Umwandlung) für sie nur einen der durch `Days` definierten Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e900-120">If the variable `meetingDay` is of type `Days`, then (without an explicit cast) you can only assign it one of the values defined by `Days`.</span></span> <span data-ttu-id="6e900-121">Und wenn sich der Sitzungstag ändert, können Sie einen neuen Wert von `Days` auf `meetingDay` zuweisen:</span><span class="sxs-lookup"><span data-stu-id="6e900-121">And if the meeting day changes, you can assign a new value from `Days` to `meetingDay`:</span></span>  
  
 <span data-ttu-id="6e900-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e900-123">Es ist möglich, einen beliebigen ganzzahligen Wert an `meetingDay` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e900-123">It is possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="6e900-124">Diese Codezeile ergibt z.B. keinen Fehler: `meetingDay = (Days) 42`.</span><span class="sxs-lookup"><span data-stu-id="6e900-124">For example, this line of code does not produce an error: `meetingDay = (Days) 42`.</span></span> <span data-ttu-id="6e900-125">Allerdings sollten Sie dies nicht tun, da implizit erwartet wird, dass eine Enumerationensvariable nur einen der von enum definierten Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="6e900-125">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="6e900-126">Einen beliebigen Wert einer Variablen eines Enumerationstyps zuzuweisen bedeutet, ein hohes Fehlerrisiko einzuführen.</span><span class="sxs-lookup"><span data-stu-id="6e900-126">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>  
  
 <span data-ttu-id="6e900-127">Sie können den Elementen in der Enumeratorliste eines Enumerationstyps Werte zuweisen, und Sie können auch berechnete Werte verwenden:</span><span class="sxs-lookup"><span data-stu-id="6e900-127">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>  
  
 <span data-ttu-id="6e900-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span></span>  
  
## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="6e900-129">Enumerationstypen als Bitflags</span><span class="sxs-lookup"><span data-stu-id="6e900-129">Enumeration Types as Bit Flags</span></span>  
 <span data-ttu-id="6e900-130">Sie können einen Enumerationstyp zum Definieren von Bitflags verwenden. Dadurch kann eine Instanz des Enumerationstyps eine beliebige Kombination der Werte speichern, die in der Enumeratorliste definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e900-130">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="6e900-131">(Natürlich können einige Kombinationen nicht sinnvoll oder in Ihrem Programmcode nicht zulässig sein.)</span><span class="sxs-lookup"><span data-stu-id="6e900-131">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>  
  
 <span data-ttu-id="6e900-132">Sie erstellen ein Bitflags-Enum durch Anwenden des Attributs <xref:System.FlagsAttribute?displayProperty=fullName> und definieren die Werte entsprechend, damit die bitweisen Operationen `AND`, `OR`, `NOT` und `XOR` ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="6e900-132">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=fullName> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="6e900-133">In einem Bitflag-Enum ist eine benannte Konstante mit dem Wert Null enthalten, das bedeutet, dass „keine Flags festgelegt sind“.</span><span class="sxs-lookup"><span data-stu-id="6e900-133">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="6e900-134">Geben Sie einem Flag keinen Wert Null, wenn es nicht bedeutet, dass „keine Flags festgelegt sind“.</span><span class="sxs-lookup"><span data-stu-id="6e900-134">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>  
  
 <span data-ttu-id="6e900-135">Im folgenden Beispiel ist eine andere Version der `Days`-Enum mit dem Namen `Days2` definiert.</span><span class="sxs-lookup"><span data-stu-id="6e900-135">In the following example, another version of the `Days` enum, which is named `Days2`, is defined.</span></span> <span data-ttu-id="6e900-136">`Days2` verfügt über das `Flags`-Attribut, und jedem Wert wird die nächste höhere Potenz von 2 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6e900-136">`Days2` has the `Flags` attribute and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="6e900-137">Dies ermöglicht Ihnen die Erstellung einer `Days2`-Variable, deren Wert `Days2.Tuesday` und `Days2.Thursday` ist.</span><span class="sxs-lookup"><span data-stu-id="6e900-137">This enables you to create a `Days2` variable whose value is `Days2.Tuesday` and `Days2.Thursday`.</span></span>  
  
 <span data-ttu-id="6e900-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span></span>  
  
 <span data-ttu-id="6e900-139">Um ein Flag für einen enum festzulegen, verwenden Sie den bitweisen `OR` Operator, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e900-139">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>  
  
 <span data-ttu-id="6e900-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span></span>  
  
 <span data-ttu-id="6e900-141">Verwenden Sie einen bitweisen `AND`-Vorgang, wie im folgenden Beispiel gezeigt, um zu bestimmen, ob ein bestimmtes Flag festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="6e900-141">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>  
  
 <span data-ttu-id="6e900-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span></span>  
  
 <span data-ttu-id="6e900-143">Weitere Informationen zu den notwendigen Überlegungen beim Definieren von Enumerationstypen mit dem <xref:System.FlagsAttribute?displayProperty=fullName>-Attribut finden Sie unter <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6e900-143">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=fullName> attribute, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="6e900-144">Verwenden der Methoden System.Enum zum Ermitteln und Bearbeiten der Enumerationswerte</span><span class="sxs-lookup"><span data-stu-id="6e900-144">Using the System.Enum Methods to Discover and Manipulate Enum Values</span></span>  
 <span data-ttu-id="6e900-145">Alle Enumerationen sind Instanzen des Typs <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6e900-145">All enums are instances of the <xref:System.Enum?displayProperty=fullName> type.</span></span> <span data-ttu-id="6e900-146">Sie können keine neuen Klassen von <xref:System.Enum?displayProperty=fullName> ableiten, aber Sie können die zugehörigen Methoden verwenden, um Informationen zu ermitteln und Werte in einer enum-Instanz zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e900-146">You cannot derive new classes from <xref:System.Enum?displayProperty=fullName>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>  
  
 <span data-ttu-id="6e900-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e900-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span></span>  
  
 <span data-ttu-id="6e900-148">Weitere Informationen finden Sie unter <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6e900-148">For more information, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="6e900-149">Sie können auch mithilfe einer Erweiterungsmethode eine neue Methode für ein enum erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e900-149">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="6e900-150">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6e900-150">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="6e900-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e900-151">See Also</span></span>  
 <span data-ttu-id="6e900-152"><xref:System.Enum?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e900-152"><xref:System.Enum?displayProperty=fullName></span></span>   
 <span data-ttu-id="6e900-153">[C#-Programmierhandbuch](../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e900-153">[C# Programming Guide](../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="6e900-154">enum</span><span class="sxs-lookup"><span data-stu-id="6e900-154">enum</span></span>](../../csharp/language-reference/keywords/enum.md)

