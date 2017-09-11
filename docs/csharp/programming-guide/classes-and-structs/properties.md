---
title: Eigenschaften (C#-Programmierhandbuch)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
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
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="29981-102">Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="29981-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="29981-103">Eine Eigenschaft ist ein Member, das einen flexiblen Mechanismus zum Lesen, Schreiben oder Berechnen des Werts eines privaten Felds bietet.</span><span class="sxs-lookup"><span data-stu-id="29981-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="29981-104">Eigenschaften können wie öffentliche Datenmember verwendet werden, es sind jedoch spezielle Methoden namens *Accessoren*.</span><span class="sxs-lookup"><span data-stu-id="29981-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="29981-105">Dies ermöglicht den problemlosen Datenzugriff und unterstützt weiterhin die Sicherheit und Flexibilität der Methoden.</span><span class="sxs-lookup"><span data-stu-id="29981-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="29981-106">Übersicht über Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29981-106">Properties overview</span></span>  
  
- <span data-ttu-id="29981-107">Mithilfe von Eigenschaften kann eine Klasse eine öffentliche Methode zum Abrufen und Festlegen von Werten verfügbar machen und dabei den Implementierungs- oder Verifizierungscode ausblenden.</span><span class="sxs-lookup"><span data-stu-id="29981-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="29981-108">Eine [get](../../../csharp/language-reference/keywords/get.md)-Eigenschaftenaccessor wird verwendet, um den Wert der Eigenschaft zurückzugeben. Ein [set](../../../csharp/language-reference/keywords/set.md)-Eigenschaftenaccessor wird verwendet, um einen neuen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="29981-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="29981-109">Diese Zugriffsmethoden können über verschiedene Zugriffsebenen verfügen.</span><span class="sxs-lookup"><span data-stu-id="29981-109">These accessors can have different access levels.</span></span> <span data-ttu-id="29981-110">Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="29981-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="29981-111">Das [value](../../../csharp/language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Accessor zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="29981-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="29981-112">Eigenschaften können sein: *Lesen/Schreiben* (beide verfügen über einen `get`- und `set`-Accessor), *schreibgeschützt* (verfügen über einen `get`-Accessor, jedoch keinen `set`-Accessor), oder *lesegeschützt* (verfügen über einen `set`-Accessor, jedoch keinen `get` Accessor).</span><span class="sxs-lookup"><span data-stu-id="29981-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="29981-113">Lesegeschützte Eigenschaften sind selten und werden am häufigsten verwendet, um den Zugriff auf vertrauliche Daten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="29981-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="29981-114">Einfache Eigenschaften, die keinen benutzerdefinierten Accessorcode erfordern können implementiert werden, entweder als Ausdruckstextdefinitionen oder als [automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="29981-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="29981-115">Eigenschaften mit Unterstützungsfeldern</span><span class="sxs-lookup"><span data-stu-id="29981-115">Properties with backing fields</span></span>

<span data-ttu-id="29981-116">Ein grundlegendes Muster zum Implementieren einer Eigenschaft umfasst ein privates Unterstützungsfeld zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="29981-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="29981-117">Der `get`-Accessor gibt den Wert des privaten Felds zurück, und der `set`-Accessor kann die Validierung einiger Daten ausführen, bevor er dem privaten Feld einen Wert zuweist.</span><span class="sxs-lookup"><span data-stu-id="29981-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="29981-118">Beide Accessoren führen möglicherweise eine Konvertierung oder eine Berechnung der Daten aus, bevor sie gespeichert oder zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="29981-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="29981-119">Dieses Muster wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="29981-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="29981-120">In diesem Beispiel stellt die `TimePeriod`-Klasse ein Zeitintervall dar.</span><span class="sxs-lookup"><span data-stu-id="29981-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="29981-121">Intern speichert die Klasse das Zeitintervall in Sekunden in einem privaten Feld mit dem Namen `seconds`.</span><span class="sxs-lookup"><span data-stu-id="29981-121">Internally, the class stores the time interval in seconds in a private field named `seconds`.</span></span> <span data-ttu-id="29981-122">Eine Schreib-Lese-Eigenschaft mit dem Namen `Hours` ermöglicht dem Kunden, das Zeitintervall in Stunden anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29981-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="29981-123">Die `get`- und `set`-Accessoren führen jeweils die notwendige Konvertierung zwischen Stunden und Sekunden durch.</span><span class="sxs-lookup"><span data-stu-id="29981-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="29981-124">Darüber hinaus prüft der `set`-Accessor die Daten, und löst eine @System.ArgumentOutOfRangeException aus, wenn die Anzahl von Stunden ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="29981-124">In addition, the `set` accessor validates the data and throws an @System.ArgumentOutOfRangeException if the number of hours is invalid.</span></span> 
   
 <span data-ttu-id="29981-125">[!code-cs[Eigenschaften#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="29981-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="29981-126">Ausdruckstextdefinitionen</span><span class="sxs-lookup"><span data-stu-id="29981-126">Expression body definitions</span></span>  

 <span data-ttu-id="29981-127">Häufig bestehen Eigenschaftenaccessoren aus einzeilige Anweisungen, die gerade das Ergebnis eines Ausdrucks zuweisen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="29981-127">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="29981-128">Sie können diese Eigenschaften als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="29981-128">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="29981-129">Ausdruckstextdefinitionen bestehen aus dem `=>`-Symbol, gefolgt von dem Ausdruck, der der Eigenschaft zugewiesen oder aus dieser abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="29981-129">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="29981-130">Beginnend mit dem C# 6, können schreibgeschützte Eigenschaften den `get`-Accessor als Ausdruckskörpermember implementieren.</span><span class="sxs-lookup"><span data-stu-id="29981-130">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="29981-131">In diesem Fall werden weder das `get`-Accessorschlüsselwort noch das `return`-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="29981-131">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="29981-132">Das folgende Beispiel implementiert die schreibgeschützte `Name`-Eigenschaft als ein Ausdruckskörpermember.</span><span class="sxs-lookup"><span data-stu-id="29981-132">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 <span data-ttu-id="29981-133">[!code-cs[Eigenschaften#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="29981-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span></span>  

 <span data-ttu-id="29981-134">Beginnen mit C# 7, könne jeweils der `get`- und `set`-Accessor als Ausdruckskörpermember implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="29981-134">Starting with C# 7, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="29981-135">In diesem Fall müsse die `get`- und `set`-Schlüsselwörter vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="29981-135">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="29981-136">Das folgende Beispiel veranschaulicht die Verwendung von Ausdruckstextdefinitionen für beide Accessoren.</span><span class="sxs-lookup"><span data-stu-id="29981-136">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="29981-137">Beachten Sie, dass das `return`-Schlüsselwort nicht mit dem `get`-Accessor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29981-137">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  <span data-ttu-id="29981-138">[!code-cs[Eigenschaften#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="29981-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span></span>  

## <a name="auto-implemented-properties"></a><span data-ttu-id="29981-139">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29981-139">Auto-implemented properties</span></span>

<span data-ttu-id="29981-140">In einigen Fällen weisen die Eigenschaft `get`- und `set`-Accessoren nur einen Wert zu oder rufen einen Wert aus einem Unterstützungsfeld ab, ohne zusätzliche Logik.</span><span class="sxs-lookup"><span data-stu-id="29981-140">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="29981-141">Mithilfe von automatisch implementierten Eigenschaften können Sie Ihren Code vereinfachen, während der C#-Compiler das Unterstützungsfeld für Sie transparent bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="29981-141">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="29981-142">Wenn eine Eigenschaft jeweils über einen `get`- und `set`-Accessor verfügt, müssen beide automatisch implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="29981-142">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="29981-143">Definieren Sie eine automatisch implementierte Eigenschaft mithilfe der `get`- und `set`-Schlüsselwörter ohne jede Implementierung.</span><span class="sxs-lookup"><span data-stu-id="29981-143">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="29981-144">Im folgenden Beispiel wird das vorherige Beispiel wiederholt, außer das `Name` und `Price` automatisch implementierte Eigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="29981-144">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="29981-145">Beachten Sie, dass das Beispiel auch den parametrisierten Konstruktor entfernt, damit `SaleItem`-Objekte jetzt mit einem Aufruf vom Standardkonstruktor und vom [Objektinitialisierer](object-and-collection-initializers.md) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="29981-145">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the default constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  <span data-ttu-id="29981-146">[!code-cs[Eigenschaften#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="29981-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span></span>  

## <a name="related-sections"></a><span data-ttu-id="29981-147">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="29981-147">Related sections</span></span>  
  
-   [<span data-ttu-id="29981-148">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29981-148">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="29981-149">Schnittstelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="29981-149">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="29981-150">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="29981-150">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="29981-151">Einschränken des Zugriffsmethodenzugriffs</span><span class="sxs-lookup"><span data-stu-id="29981-151">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [<span data-ttu-id="29981-152">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29981-152">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="29981-153">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="29981-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29981-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29981-154">See also</span></span>
 <span data-ttu-id="29981-155">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="29981-155">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="29981-156">[Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="29981-156">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="29981-157">[Indexer](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="29981-157">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="29981-158">[get-Schlüsselwort](../../../csharp/language-reference/keywords/get.md)  </span><span class="sxs-lookup"><span data-stu-id="29981-158">[get keyword](../../../csharp/language-reference/keywords/get.md)  </span></span>  
 [<span data-ttu-id="29981-159">set-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="29981-159">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)    

