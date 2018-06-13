---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 75225e624abdd3dc0862a04fae409da48b3f0d1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563414"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="c34b9-102">x:FactoryMethod-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c34b9-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="c34b9-103">Gibt eine Methode als einen Konstruktor, den ein XAML-Prozessor verwenden soll, um ein Objekt nach seiner Unterstützungstyp auflösen zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c34b9-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="c34b9-104">Verwendung von XAML-Attributen, keine X: Arguments</span><span class="sxs-lookup"><span data-stu-id="c34b9-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="c34b9-105">Verwendung von XAML-Attributen, X: Arguments als Element(e)</span><span class="sxs-lookup"><span data-stu-id="c34b9-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c34b9-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="c34b9-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="c34b9-107">Die Methode Zeichenfolgennamen einer Methode, die XAML-Prozessoren zum Initialisieren der Instanz aufrufen als angegeben `object`.</span><span class="sxs-lookup"><span data-stu-id="c34b9-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="c34b9-108">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c34b9-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="c34b9-109">Ein oder mehrere Objektelemente für Objekte, die Parameter der Factory-Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="c34b9-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="c34b9-110">Die Reihenfolge ist wichtig; Es gibt an, die Reihenfolge, in der Argumente an die Factory-Methode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c34b9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c34b9-111">Remarks</span></span>  
 <span data-ttu-id="c34b9-112">Wenn `methodname` ist eine Instanzmethode kann nicht qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="c34b9-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="c34b9-113">Statische Methoden als Factorymethoden werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="c34b9-114">Wenn `methodname` ist eine statische Methode `methodname` dient als ein *TypeName*. *Methodenname* zusammen, auf dem *TypeName* benennt die Klasse, die die statische Factorymethode definiert.</span><span class="sxs-lookup"><span data-stu-id="c34b9-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="c34b9-115">*TypeName* Präfix qualifiziert sein, wenn auf einen Typ in einem zugeordneten Xmlns verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="c34b9-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="c34b9-116">*TypeName* kann ein anderen Typ als `typeof(``object``)`.</span><span class="sxs-lookup"><span data-stu-id="c34b9-116">*typeName* can be a different type than `typeof(``object``)`.</span></span>  
  
 <span data-ttu-id="c34b9-117">Die Factory-Methode muss eine deklarierte öffentliche Methode des Typs, der die relevante Objektelement unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="c34b9-118">Die Factory-Methode muss es sich um eine Instanz zurückgeben, die auf das entsprechende Objekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c34b9-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="c34b9-119">Factorymethoden sollten nie null zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c34b9-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="c34b9-120">`x:Arguments` Ein Prinzip der beste Übereinstimmung für Signaturen von Factorymethoden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c34b9-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="c34b9-121">Die Parameteranzahl Abgleich zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c34b9-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="c34b9-122">Gibt es ist mehr als eine mögliche Entsprechung für ein Parameteranzahl, Parametertyp ausgewertet und die beste Übereinstimmung ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="c34b9-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="c34b9-123">Wenn Mehrdeutigkeiten nach dieser Phase der Auswertung immer noch vorhanden ist, ist die XAML-Prozessorverhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="c34b9-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="c34b9-124">Die `x:FactoryMethod` Elementverwendung ist nicht Eigenschaftenelementen insofern typisch, da die Richtlinie Markup nicht des enthaltenden Objektelements Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="c34b9-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="c34b9-125">Es wird davon ausgegangen, dass Elementverwendung ist weniger gebräuchlich als Attributen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="c34b9-126">`x:Arguments` (Attribut- oder Elementwert Verwendung) verwendet werden kann, zusammen mit `x:FactoryMethod` Elementverwendung, aber dies wird nicht ausdrücklich angezeigt in den Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="c34b9-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="c34b9-127">`x:FactoryMethod` wie ein Element alle anderen Eigenschaftenelemente vorangestellt werden muss, müssen alle vorausgehen `x:Arguments` auch als Elemente angegeben und muss alle Inhalte bzw. innere Text/Initialisierungstext vorangehen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34b9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c34b9-128">See Also</span></span>  
 [<span data-ttu-id="c34b9-129">x:Arguments-Direktive</span><span class="sxs-lookup"><span data-stu-id="c34b9-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
