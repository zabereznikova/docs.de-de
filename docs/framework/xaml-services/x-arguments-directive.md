---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5bcd629e306169c1f7a61a316d76203827a2d0fe
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364268"
---
# <a name="xarguments-directive"></a><span data-ttu-id="b4759-102">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4759-102">x:Arguments Directive</span></span>
<span data-ttu-id="b4759-103">Pakete erstellen Argumente für eine nicht parameterlose konstruktorobjektelement-Deklaration in XAML oder für eine Factorymethoden-Objekt Deklaration.</span><span class="sxs-lookup"><span data-stu-id="b4759-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="b4759-104">Verwendung von XAML-Elementen (nicht parameterloser Konstruktor)</span><span class="sxs-lookup"><span data-stu-id="b4759-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="b4759-105">Verwendung von XAML-Elementen (Factory-Methode)</span><span class="sxs-lookup"><span data-stu-id="b4759-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b4759-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="b4759-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="b4759-107">Ein oder mehrere Objekt Elemente, die Argumente angeben, die an den zugrunde liegenden nicht parameterlosen Konstruktor oder die Factorymethode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4759-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="b4759-108">Die typische Verwendung besteht darin, den Initialisierungs Text innerhalb der Objekt Elemente zu verwenden, um die eigentlichen Argument Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b4759-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="b4759-109">Siehe den Abschnitt "Beispiele".</span><span class="sxs-lookup"><span data-stu-id="b4759-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="b4759-110">Die Reihenfolge der Elemente ist von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="b4759-110">The order of the elements is significant.</span></span> <span data-ttu-id="b4759-111">Die XAML-Typen müssen mit den Typen und der Typreihenfolge der Überladung des Unterstützungs Konstruktors oder der Factorymethode identisch sein.</span><span class="sxs-lookup"><span data-stu-id="b4759-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="b4759-112">Der Name der Factorymethode, die alle `x:Arguments` Argumente verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="b4759-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="b4759-113">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b4759-113">Dependencies</span></span>  
 <span data-ttu-id="b4759-114">`x:FactoryMethod`kann den Bereich und das Verhalten ändern `x:Arguments` , wenn angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4759-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="b4759-115">Wenn kein `x:FactoryMethod` angegeben ist, `x:Arguments` gilt für Alternative (nicht standardmäßige) Signaturen der Unterstützungs Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="b4759-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="b4759-116">Wenn `x:FactoryMethod` angegeben wird, `x:Arguments` gilt für eine Überladung der benannten Methode.</span><span class="sxs-lookup"><span data-stu-id="b4759-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4759-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4759-117">Remarks</span></span>  
 <span data-ttu-id="b4759-118">XAML 2006 kann die nicht standardmäßige Initialisierung durch Initialisierungs Text unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b4759-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="b4759-119">Die praktische Anwendung einer Initialisierungs Methode für die Erstellung von Text ist jedoch begrenzt.</span><span class="sxs-lookup"><span data-stu-id="b4759-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="b4759-120">Der Initialisierungs Text wird als eine einzelne Text Zeichenfolge behandelt. Daher wird nur die Funktion für eine einzelne Parameter Initialisierung hinzugefügt, es sei denn, es ist ein Typkonverter für das Konstruktions Verhalten definiert, mit dem benutzerdefinierte Informationselemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b4759-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="b4759-121">Außerdem ist die Text Zeichenfolge für die Objekt Logik möglicherweise ein angegebener Standard Typkonverter eines XAML-Parsers für die Verarbeitung primitiver Elemente, die keine echte Zeichenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="b4759-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="b4759-122">Die `x:Arguments` XAML-Verwendung ist im typischen Sinn nicht die Verwendung von Eigenschafts Elementen, da das direktivenmarkup nicht auf den Typ des enthaltenden Objekt Elements verweist.</span><span class="sxs-lookup"><span data-stu-id="b4759-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="b4759-123">Es ähnelt eher anderen Direktiven, z `x:Code` . b. wenn das Element einen Bereich, in dem das Markup interpretiert werden soll, als den Standardwert für den untergeordneten Inhalt demarkiert.</span><span class="sxs-lookup"><span data-stu-id="b4759-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="b4759-124">In diesem Fall kommuniziert der XAML-Typ jedes Objekt Elements mit Informationen zu den Argument Typen, die von XAML-Parser verwendet werden, um zu bestimmen, auf welche spezifische konstruktorfactorymethodensignatur ein `x:Arguments` Verwendungs Versuch verweist.</span><span class="sxs-lookup"><span data-stu-id="b4759-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="b4759-125">`x:Arguments`für ein Objekt Element, das erstellt wird, muss allen anderen Eigenschaften Elementen, Inhalten, inneren Text oder Initialisierungs Zeichenfolgen des Object-Elements vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="b4759-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="b4759-126">Die Objekt Elemente in `x:Arguments` können Attribute und Initialisierungs Zeichenfolgen enthalten, die von diesem XAML-Typ und dessen unterstützungskonstruktor oder Factorymethode zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b4759-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="b4759-127">Für das-Objekt oder das-Argument können Sie benutzerdefinierte XAML-Typen oder XAML-Typen angeben, die sich anderweitig außerhalb des standardmäßigen XAML-Namespace befinden, indem Sie auf festgelegte Präfix Zuordnungen verweisen.</span><span class="sxs-lookup"><span data-stu-id="b4759-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="b4759-128">XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, `x:Arguments` wie die in angegebenen Argumente zum Erstellen eines-Objekts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4759-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="b4759-129">Wenn `x:FactoryMethod` angegeben wird, werden Informationen mit dem angegebenen `x:FactoryMethod` verglichen (Beachten Sie, dass der `x:FactoryMethod` Wert von der Methodenname ist und die benannte Methode über Ladungen aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="b4759-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="b4759-130">Wenn `x:FactoryMethod` nicht angegeben wird, werden Informationen mit dem Satz aller öffentlichen Konstruktorüberladungen des-Objekts verglichen.</span><span class="sxs-lookup"><span data-stu-id="b4759-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="b4759-131">Die XAML-Verarbeitungslogik vergleicht dann die Anzahl von Parametern und wählt die Überladung mit passender Stelligkeit aus.</span><span class="sxs-lookup"><span data-stu-id="b4759-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="b4759-132">Wenn mehrere Übereinstimmungen vorhanden sind, sollte der XAML-Prozessor die Typen der Parameter basierend auf den XAML-Typen der bereitgestellten Objekt Elemente vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b4759-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="b4759-133">Wenn noch mehr als eine Entsprechung vorhanden ist, ist das XAML-Prozessor Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="b4759-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="b4759-134">Wenn eine `x:FactoryMethod` angegeben ist, aber die Methode nicht aufgelöst werden kann, sollte ein XAML-Prozessor eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="b4759-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="b4759-135">Eine XAML-Attribut `<x:Arguments>string</x:Arguments>` Verwendung ist technisch möglich.</span><span class="sxs-lookup"><span data-stu-id="b4759-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="b4759-136">Dies stellt jedoch keine Funktionen bereit, die über das, was andernfalls durch Initialisierungs Text und Typkonverter möglich ist, hinausgehen kann, und die Verwendung dieser Syntax ist nicht die Entwurfs Absicht der Funktionen der XAML 2009-Factorymethode.</span><span class="sxs-lookup"><span data-stu-id="b4759-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b4759-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b4759-137">Examples</span></span>  
 <span data-ttu-id="b4759-138">Das folgende Beispiel zeigt eine nicht parameterlose Konstruktorsignatur, dann die XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="b4759-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="b4759-139">Das folgende Beispiel zeigt die Signatur einer zielfactorymethode und dann die XAML-Verwendung von, die auf `x:Arguments` diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="b4759-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b4759-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4759-140">See also</span></span>

- [<span data-ttu-id="b4759-141">Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten</span><span class="sxs-lookup"><span data-stu-id="b4759-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="b4759-142">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4759-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
