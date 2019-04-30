---
title: x:Arguments-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: a87542513ffeeec7efc526d4218f921d1b7579a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953958"
---
# <a name="xarguments-directive"></a><span data-ttu-id="2e609-102">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e609-102">x:Arguments Directive</span></span>
<span data-ttu-id="2e609-103">Pakete Konstruktionsargumente für eine Elementdeklaration für nicht-Standardkonstruktors Objekt in XAML oder für eine Factory Methodendeklaration-Objekt.</span><span class="sxs-lookup"><span data-stu-id="2e609-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="2e609-104">XAML-Elementverwendung (nicht standardmäßigen Konstruktor)</span><span class="sxs-lookup"><span data-stu-id="2e609-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="2e609-105">XAML-Elementverwendung (Factorymethode)</span><span class="sxs-lookup"><span data-stu-id="2e609-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2e609-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="2e609-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="2e609-107">Eine oder mehrere Object-Elemente, die angeben, um die dahinter liegende nicht standardmäßigen Konstruktor oder auf die werkseinstellungen-Methode zu übergebenden Argumente.</span><span class="sxs-lookup"><span data-stu-id="2e609-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="2e609-108">Typischerweise werden Initialisierungstext in Object-Elemente zu verwenden, um die Werte des tatsächlichen Arguments angeben.</span><span class="sxs-lookup"><span data-stu-id="2e609-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="2e609-109">Siehe Abschnitt "Beispiele".</span><span class="sxs-lookup"><span data-stu-id="2e609-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="2e609-110">Die Reihenfolge der Elemente ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="2e609-110">The order of the elements is significant.</span></span> <span data-ttu-id="2e609-111">Die XAML-Typen in der Reihenfolge müssen den Typen entsprechen, und geben Sie die Reihenfolge der Sicherung oder die Factorymethode Überladung der.</span><span class="sxs-lookup"><span data-stu-id="2e609-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="2e609-112">Der Name der Factory-Methode, die alle verarbeiten soll `x:Arguments` Argumente.</span><span class="sxs-lookup"><span data-stu-id="2e609-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="2e609-113">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="2e609-113">Dependencies</span></span>  
 <span data-ttu-id="2e609-114">`x:FactoryMethod` können den Bereich und das Verhalten ändern, in denen `x:Arguments` gilt.</span><span class="sxs-lookup"><span data-stu-id="2e609-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="2e609-115">Wenn kein `x:FactoryMethod` angegeben wird, `x:Arguments` gilt für den alternativen (nicht standardmäßige) Signaturen der dahinter liegende Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="2e609-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="2e609-116">Wenn `x:FactoryMethod` angegeben wird, `x:Arguments` an eine Überladung der die benannte Methode angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e609-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e609-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e609-117">Remarks</span></span>  
 <span data-ttu-id="2e609-118">XAML 2006 können nicht standardmäßigen Initialisierung durch Initialisierungstext unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2e609-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="2e609-119">Die praktische Anwendung für die eine Initialisierung Text Konstruktion-Methode ist jedoch beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e609-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="2e609-120">Initialisierungstext wird als eine einzelne Zeichenfolge behandelt. aus diesem Grund wird nur Funktionen für die Initialisierung eines einzelnen Parameter, wenn ein Typkonverter für das Verhalten der Erstellung definiert ist, die benutzerdefinierten Informationen-Elemente und benutzerdefinierte Trennzeichen aus der Zeichenfolge analysieren können.</span><span class="sxs-lookup"><span data-stu-id="2e609-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="2e609-121">Darüber hinaus ist die Textzeichenfolge, Objekt-Logik möglicherweise einen angegebenen XAML-Parser native Standardtypkonverter für die Behandlung von primitiven als eine Zeichenfolge "true".</span><span class="sxs-lookup"><span data-stu-id="2e609-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="2e609-122">Die `x:Arguments` XAML-Verwendung ist nicht Eigenschaftselementverwendung im typischen Sinn, da das Markup-Direktive nicht der enthaltenden Objekt Typ des Elements verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2e609-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="2e609-123">Es ist z. B. anderen Direktiven `x:Code` , in dem das Element einen Bereich, in denen das Markup interpretiert werden soll, wie Sie sich als den Standardwert für den untergeordneten Inhalt, demarks.</span><span class="sxs-lookup"><span data-stu-id="2e609-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="2e609-124">In diesem Fall der XAML-Typ, der jedes Objektelement Informationen zu den Argumenttypen, die vom XAML-Parser verwendet wird, um zu bestimmen, welche bestimmten Konstruktor Factory-Methodensignatur kommuniziert eine `x:Arguments` Nutzung zu verweisen versucht.</span><span class="sxs-lookup"><span data-stu-id="2e609-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="2e609-125">`x:Arguments` für ein Objektelement muss erstellt werden alle anderen Eigenschaftenelemente, Inhalte, inneren Text oder Initialisierungszeichenfolgen des Objektelements vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="2e609-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="2e609-126">Die Objektelemente in `x:Arguments` können einschließen, Attribute und Initialisierungszeichenfolgen, gemäß diesen XAML-Typ und die Sicherung oder die Factorymethode-Methode.</span><span class="sxs-lookup"><span data-stu-id="2e609-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="2e609-127">Für das Objekt oder die Argumente können Sie benutzerdefinierte XAML-Typen oder XAML-Typen, die andernfalls außerhalb des Standard-XAML-Namespaces sind durch Verweisen auf etablierten Präfix-Zuordnungen angeben.</span><span class="sxs-lookup"><span data-stu-id="2e609-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="2e609-128">XAML-Prozessoren verwenden die folgenden Richtlinien, um zu bestimmen, wie die Argumente in angegeben `x:Arguments` sollte zum Erstellen eines Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e609-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="2e609-129">Wenn `x:FactoryMethod` angegeben ist, werden Informationen verglichen mit dem angegebenen `x:FactoryMethod` (Beachten Sie, dass der Wert des `x:FactoryMethod` ist der Name der Methode, und die benannte Methode kann Überladungen.</span><span class="sxs-lookup"><span data-stu-id="2e609-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="2e609-130">Wenn `x:FactoryMethod` nicht angegeben ist, Informationen auf den Satz aller Überladungen suchen öffentlicher Konstruktor des Objekts verglichen.</span><span class="sxs-lookup"><span data-stu-id="2e609-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="2e609-131">XAML-Verarbeitungslogik vergleicht die Anzahl von Parametern und die Überladung mit übereinstimmenden Stelligkeit auswählt.</span><span class="sxs-lookup"><span data-stu-id="2e609-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="2e609-132">Wenn mehr als eine Übereinstimmung vorliegt, sollten der XAML-Prozessor die Typen der Parameter auf Grundlage der XAML-Typen, Elemente der bereitgestellten Objekt vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2e609-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="2e609-133">Wenn Sie noch mehr als eine Übereinstimmung vorliegt, ist das XAML-Prozessor-Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="2e609-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="2e609-134">Wenn eine `x:FactoryMethod` angegeben ist, aber die Methode kann nicht aufgelöst werden, ein XAML-Prozessor sollte eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="2e609-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="2e609-135">Ein XAML-Attributverwendung `<x:Arguments>string</x:Arguments>` ist es technisch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="2e609-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="2e609-136">Allerdings dadurch, dass keine Funktionen über was andernfalls über Initialisierung und -Typkonverter durchgeführt werden konnte, und mit dieser Syntax ist nicht der Zweck der XAML 2009-Funktionen für die Factory-Methode.</span><span class="sxs-lookup"><span data-stu-id="2e609-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e609-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2e609-137">Examples</span></span>  
 <span data-ttu-id="2e609-138">Das folgende Beispiel zeigt einen nicht standardmäßigen Konstruktor Signatur, und klicken Sie dann auf die XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="2e609-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="2e609-139">Das folgende Beispiel zeigt die Signatur einer Ziel-Factory-Methode, und klicken Sie dann auf die XAML-Verwendung von `x:Arguments` , die auf diese Signatur zugreift.</span><span class="sxs-lookup"><span data-stu-id="2e609-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e609-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e609-140">See also</span></span>

- [<span data-ttu-id="2e609-141">Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten</span><span class="sxs-lookup"><span data-stu-id="2e609-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="2e609-142">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2e609-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
