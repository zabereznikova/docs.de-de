---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432833"
---
# <a name="xarguments-directive"></a><span data-ttu-id="6bd56-102">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6bd56-102">x:Arguments Directive</span></span>

<span data-ttu-id="6bd56-103">Verpackt Konstruktionsargumente für eine nicht parametrlose Konstruktorobjektelementdeklaration in XAML oder für eine Factory-Methodenobjektdeklaration.</span><span class="sxs-lookup"><span data-stu-id="6bd56-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="6bd56-104">XAML-Elementverwendung (nicht parameterloser Konstruktor)</span><span class="sxs-lookup"><span data-stu-id="6bd56-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6bd56-105">XAML-Elementverwendung (Werksmethode)</span><span class="sxs-lookup"><span data-stu-id="6bd56-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="6bd56-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="6bd56-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="6bd56-107">Mindestens ein Objektelement, das Argumente angibt, die an den nicht parameterlosen Konstruktor oder die Factorymethode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6bd56-108">Typische Verwendung besteht darin, Initialisierungstext innerhalb der Objektelemente zu verwenden, um die tatsächlichen Argumentwerte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6bd56-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6bd56-109">Siehe Abschnitt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="6bd56-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6bd56-110">Die Reihenfolge der Elemente ist signifikant.</span><span class="sxs-lookup"><span data-stu-id="6bd56-110">The order of the elements is significant.</span></span> <span data-ttu-id="6bd56-111">Die XAML-Typen müssen in der Reihenfolge mit den Typen und der Typreihenfolge des Sicherungskonstruktors oder der Werksmethode überlasten.</span><span class="sxs-lookup"><span data-stu-id="6bd56-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="6bd56-112">Der Name der Factorymethode, `x:Arguments` die alle Argumente verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="6bd56-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="6bd56-113">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="6bd56-113">Dependencies</span></span>

<span data-ttu-id="6bd56-114">`x:FactoryMethod`kann den Bereich und `x:Arguments` das Verhalten ändern, wo dies angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6bd56-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="6bd56-115">Wenn `x:FactoryMethod` nein `x:Arguments` angegeben ist, gilt für alternative (nicht standardmäßige) Signaturen der Sicherungskonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="6bd56-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="6bd56-116">Wenn `x:FactoryMethod` angegeben, `x:Arguments` gilt für eine Überladung der benannten Methode.</span><span class="sxs-lookup"><span data-stu-id="6bd56-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bd56-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6bd56-117">Remarks</span></span>

<span data-ttu-id="6bd56-118">XAML 2006 kann die nicht standardmäßige Initialisierung durch Initialisierungstext unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6bd56-119">Die praktische Anwendung einer Initialisierungstextkonstruktionstechnik ist jedoch begrenzt.</span><span class="sxs-lookup"><span data-stu-id="6bd56-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6bd56-120">Initialisierungstext wird als einzelne Textzeichenfolge behandelt. Daher wird nur die Funktion für eine einzelne Parameterinitialisierung hinzugefügt, es sei denn, für das Konstruktionsverhalten wird ein Typkonverter definiert, der benutzerdefinierte Informationselemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren kann.</span><span class="sxs-lookup"><span data-stu-id="6bd56-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6bd56-121">Außerdem ist die Textzeichenfolge für die Objektlogik potenziell der systemeigene Standardtypkonverter eines bestimmten XAML-Parsers für die Behandlung anderer Primitive randals als eine echte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6bd56-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="6bd56-122">Die `x:Arguments` XAML-Verwendung ist keine Eigenschaftselementverwendung im typischen Sinne, da das Direktivenmarkup nicht auf den Typ des enthaltenden Objektelements verweist.</span><span class="sxs-lookup"><span data-stu-id="6bd56-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6bd56-123">Sie ähnelt eher anderen Direktiven, z. `x:Code` B. wenn das Element einen Bereich markiert, in dem das Markup als andere als die Standardeinstellung für untergeordnete Inhalte interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6bd56-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6bd56-124">In diesem Fall übermittelt der XAML-Typ jedes Objektelements Informationen über die Argumenttypen, die von XAML-Parsern verwendet werden, um zu bestimmen, auf welche bestimmte Konstruktorfactory-Factory-Methodensignatur eine `x:Arguments` Verwendung zu verweisen versucht.</span><span class="sxs-lookup"><span data-stu-id="6bd56-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="6bd56-125">`x:Arguments`Denn ein Objektelement, das erstellt wird, muss allen anderen Eigenschaftselementen, Inhalten, inneninneren Text- oder Initialisierungszeichenfolgen des Objektelements vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6bd56-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6bd56-126">Die darin `x:Arguments` enthaltenden Objektelemente können Attribute und Initialisierungszeichenfolgen enthalten, wie von diesem XAML-Typ und seiner Sicherungskonstruktor- oder Factorymethode zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6bd56-127">Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML-Typen oder XAML-Typen angeben, die sich ansonsten außerhalb des standardmäßigen XAML-Namespace befinden, indem Sie auf etablierte Präfixzuordnungen verweisen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="6bd56-128">XAML-Prozessoren verwenden die folgenden Richtlinien, `x:Arguments` um zu bestimmen, wie die in angegebenen Argumente zum Erstellen eines Objekts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6bd56-129">Wenn `x:FactoryMethod` angegeben, werden Informationen mit `x:FactoryMethod` den angegebenen verglichen `x:FactoryMethod` (beachten Sie, dass der Wert des Methodennamens ist und die benannte Methode Überladungen aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="6bd56-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6bd56-130">Wenn `x:FactoryMethod` nicht angegeben, werden Informationen mit dem Satz aller öffentlichen Konstruktorüberladungen des Objekts verglichen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6bd56-131">Die XAML-Verarbeitungslogik vergleicht dann die Anzahl der Parameter und wählt die Überlast mit der übereinstimmenden Arity aus.</span><span class="sxs-lookup"><span data-stu-id="6bd56-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6bd56-132">Wenn mehr als eine Übereinstimmung vorhanden ist, sollte der XAML-Prozessor die Typen der Parameter basierend auf den XAML-Typen der bereitgestellten Objektelemente vergleichen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6bd56-133">Wenn immer noch mehr als eine Übereinstimmung vorhanden ist, ist das XAML-Prozessorverhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="6bd56-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6bd56-134">Wenn `x:FactoryMethod` a angegeben ist, die Methode jedoch nicht aufgelöst werden kann, sollte ein XAML-Prozessor eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="6bd56-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="6bd56-135">Eine XAML-Attributverwendung `<x:Arguments>string</x:Arguments>` ist technisch möglich.</span><span class="sxs-lookup"><span data-stu-id="6bd56-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6bd56-136">Dies bietet jedoch keine Funktionen, die über das hinausgehen, was andernfalls durch Initialisierung von Text- und Typkonvertern getan werden könnte, und die Verwendung dieser Syntax ist nicht die Entwurfsabsicht der XAML 2009-Factory-Methodenfeatures.</span><span class="sxs-lookup"><span data-stu-id="6bd56-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="6bd56-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6bd56-137">Examples</span></span>

<span data-ttu-id="6bd56-138">Das folgende Beispiel zeigt eine nicht parameterlose Konstruktorsignatur, `x:Arguments` und dann greift die XAML-Verwendung dieser Signatur auf diese Signatur zu.</span><span class="sxs-lookup"><span data-stu-id="6bd56-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="6bd56-139">Das folgende Beispiel zeigt eine Zielfactory-Methodensignatur und `x:Arguments` dann die XAML-Verwendung dieser Signatur.</span><span class="sxs-lookup"><span data-stu-id="6bd56-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="6bd56-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bd56-140">See also</span></span>

- [<span data-ttu-id="6bd56-141">Definieren benutzerdefinierter Typen für die Verwendung in .NET-XAML-Diensten</span><span class="sxs-lookup"><span data-stu-id="6bd56-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="6bd56-142">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bd56-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
