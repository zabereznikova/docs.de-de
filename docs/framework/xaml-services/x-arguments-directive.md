---
title: x:Arguments-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bb1f5986a0d9f9eb69ade0228925ec06164cee4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xarguments-directive"></a><span data-ttu-id="6250f-102">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6250f-102">x:Arguments Directive</span></span>
<span data-ttu-id="6250f-103">Pakete Konstruktionsargumente für einen nicht standardmäßigen Konstruktor Element Objektdeklaration in XAML oder eine Objektdeklaration der Factory-Methode.</span><span class="sxs-lookup"><span data-stu-id="6250f-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="6250f-104">XAML-Elementverwendung (nicht standardmäßigen Konstruktor)</span><span class="sxs-lookup"><span data-stu-id="6250f-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6250f-105">XAML-Elementverwendung (Factory-Methode)</span><span class="sxs-lookup"><span data-stu-id="6250f-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6250f-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="6250f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="6250f-107">Ein oder mehrere Objektelemente, die Argumente angeben, die an die dahinter liegende nicht standardmäßiger Konstruktor oder eine Factory-Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6250f-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6250f-108">Typische Verwendung ist, Initialisierungstext innerhalb der Objektelemente zu verwenden, um die tatsächliche Argumentwerte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6250f-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6250f-109">Siehe Abschnitt "Beispiele".</span><span class="sxs-lookup"><span data-stu-id="6250f-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6250f-110">Die Reihenfolge der Elemente ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="6250f-110">The order of the elements is significant.</span></span> <span data-ttu-id="6250f-111">Die Verwendung von XAML-Typen in der Reihenfolge müssen den Typen entsprechen und geben Sie die Reihenfolge der methodenüberladung für das dahinter liegende Konstruktor oder eine Factory.</span><span class="sxs-lookup"><span data-stu-id="6250f-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="6250f-112">Der Name der Factorymethode, die alle verarbeiten soll `x:Arguments` Argumente.</span><span class="sxs-lookup"><span data-stu-id="6250f-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="6250f-113">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="6250f-113">Dependencies</span></span>  
 <span data-ttu-id="6250f-114">`x:FactoryMethod`der Bereich und das Verhalten ändern können, in denen `x:Arguments` gilt.</span><span class="sxs-lookup"><span data-stu-id="6250f-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="6250f-115">Wenn kein `x:FactoryMethod` angegeben wird, `x:Arguments` alternativen (nicht standardmäßige) Signaturen der dahinter liegende Konstruktoren betrifft.</span><span class="sxs-lookup"><span data-stu-id="6250f-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="6250f-116">Wenn `x:FactoryMethod` angegeben wird, `x:Arguments` an eine Überladung der Methode mit dem Namen gilt.</span><span class="sxs-lookup"><span data-stu-id="6250f-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6250f-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6250f-117">Remarks</span></span>  
 <span data-ttu-id="6250f-118">XAML 2006 können nicht standardmäßigen Initialisierung durch Initialisierungstext unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6250f-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6250f-119">Die praktische Anwendung eine Initialisierung Text Konstruktion Technik ist jedoch beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6250f-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6250f-120">Initialisierungstext wird als eine einzelne Zeichenfolge behandelt; Daher fügt er nur-Funktion für die Initialisierung eines einzelnen Parameter, wenn ein Typkonverter für das Konstruktionsverhalten definiert ist, die benutzerdefinierte Informationselementen und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren können.</span><span class="sxs-lookup"><span data-stu-id="6250f-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6250f-121">Darüber hinaus ist die Textzeichenfolge, Objekt-Logik potenziell einen angegebenen XAML-Parser systemeigene Typkonverter für das Behandeln von primitiven als eine Zeichenfolge mit "true".</span><span class="sxs-lookup"><span data-stu-id="6250f-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="6250f-122">Die `x:Arguments` XAML-Verwendung ist nicht Eigenschaftenelementen insofern typisch, da die Richtlinie Markup nicht des enthaltenden Objektelements Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="6250f-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6250f-123">Es ist z. B. andere Direktiven, die eher `x:Code` , in dem das Element ein Bereichs, in dem das Markup interpretiert werden soll, wie der Standardnummer Inhalt für untergeordnete, demarks.</span><span class="sxs-lookup"><span data-stu-id="6250f-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6250f-124">In diesem Fall der Verwendung von XAML-Typ jedes Elements des Objekts Informationen zu den Typen, die XAML-Parser verwendet wird, um zu bestimmen, welche bestimmten Konstruktor Factory-Methodensignatur kommuniziert ein `x:Arguments` Verwendung verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="6250f-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="6250f-125">`x:Arguments`für ein Object-Element muss zu erstellenden alle anderen Eigenschaftenelemente, Inhalte, innere Text oder Initialisierungszeichenfolgen des Object-Element vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="6250f-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6250f-126">Die Objektelemente in `x:Arguments` zählen Attribute und Initialisierungszeichenfolgen, gemäß diesem XAML-Typ und die dahinter liegende Konstruktor oder eine Factory-Methode.</span><span class="sxs-lookup"><span data-stu-id="6250f-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6250f-127">Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML- oder XAML-Typen, die andernfalls außerhalb der Verwendung von XAML-Standardnamespace sind durch Verweisen auf die eingerichtete/Präfix-Zuordnungen angeben.</span><span class="sxs-lookup"><span data-stu-id="6250f-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="6250f-128">Verwendung von XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die Argumente in angegeben `x:Arguments` sollte verwendet werden, um ein Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6250f-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6250f-129">Wenn `x:FactoryMethod` angegeben ist, werden die Informationen werden verglichen mit dem angegebenen `x:FactoryMethod` (Beachten Sie, dass der Wert des `x:FactoryMethod` ist der Name der Methode, und die benannte Methode kann Überladungen.</span><span class="sxs-lookup"><span data-stu-id="6250f-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6250f-130">Wenn `x:FactoryMethod` nicht angegeben ist, werden die Informationen auf den Satz von Überladungen, die alle öffentlichen Konstruktor des Objekts verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="6250f-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6250f-131">Verwendung von XAML-Verarbeitungslogik vergleicht die Anzahl von Parametern und wählt die Überladung ohne übereinstimmende Stelligkeit.</span><span class="sxs-lookup"><span data-stu-id="6250f-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6250f-132">Wenn mehr als eine Übereinstimmung vorhanden ist, sollte der XAML-Prozessor die Typen der Parameter auf Grundlage der Verwendung von XAML-Typen der bereitgestellten Objektelemente vergleichen.</span><span class="sxs-lookup"><span data-stu-id="6250f-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6250f-133">Wenn noch mehr als eine Übereinstimmung vorhanden ist, ist die Verwendung von XAML-Prozessor-Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="6250f-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6250f-134">Wenn eine `x:FactoryMethod` angegeben ist, aber die Methode kann nicht aufgelöst werden, sollte ein XAML-Prozessor eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="6250f-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="6250f-135">Eine Verwendung von XAML-Attributen `<x:Arguments>string</x:Arguments>` technisch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="6250f-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6250f-136">Allerdings Dies bietet keine Funktionen über hinaus, was andernfalls durch Initialisierung und -Typkonverter erzielt werden kann, und mithilfe dieser Syntax ist nicht die Absicht Entwurf der XAML 2009-Funktionen für die Factory-Methode.</span><span class="sxs-lookup"><span data-stu-id="6250f-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6250f-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6250f-137">Examples</span></span>  
 <span data-ttu-id="6250f-138">Das folgende Beispiel zeigt einen Standardkonstruktor, Signatur, und klicken Sie dann auf die Verwendung von XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="6250f-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="6250f-139">Das folgende Beispiel zeigt die Signatur einer Ziel-Factory-Methode, und klicken Sie dann auf die Verwendung von XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="6250f-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6250f-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6250f-140">See Also</span></span>  
 [<span data-ttu-id="6250f-141">Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten</span><span class="sxs-lookup"><span data-stu-id="6250f-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [<span data-ttu-id="6250f-142">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6250f-142">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
