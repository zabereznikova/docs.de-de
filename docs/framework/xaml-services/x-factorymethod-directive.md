---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190690"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="a36cb-102">x:FactoryMethod-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a36cb-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="a36cb-103">Gibt eine Methode als einen Konstruktor, den ein XAML-Prozessor verwenden soll, um ein Objekt zu initialisieren, nach dessen Unterstützungstyp auflösen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="a36cb-104">XAML-Attributverwendung, die keine X: Arguments</span><span class="sxs-lookup"><span data-stu-id="a36cb-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="a36cb-105">XAML-Attributverwendung, X: Arguments als Elemente</span><span class="sxs-lookup"><span data-stu-id="a36cb-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a36cb-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="a36cb-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="a36cb-107">Der Zeichenfolgenname für die Methode einer Methode, die XAML-Prozessoren aufrufen, zum Initialisieren der Instanz, die als `object`.</span><span class="sxs-lookup"><span data-stu-id="a36cb-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="a36cb-108">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="a36cb-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="a36cb-109">Eine oder mehrere Object-Elemente für Objekte, die Parameter der Factory-Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="a36cb-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="a36cb-110">Die Reihenfolge ist wichtig; Es gibt an, die Reihenfolge, in der Argumente, die an die Factorymethode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a36cb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a36cb-111">Remarks</span></span>  
 <span data-ttu-id="a36cb-112">Wenn `methodname` ist eine Instanzmethode, kann nicht qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="a36cb-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="a36cb-113">Statische Methoden als Factorymethoden werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="a36cb-114">Wenn `methodname` ist eine statische Methode, `methodname` dient als ein *TypeName*. *MethodName* Kombination aus, in denen *TypeName* benennt die Klasse, die von der statischen Factorymethode definiert.</span><span class="sxs-lookup"><span data-stu-id="a36cb-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="a36cb-115">*TypeName* möglich Präfix qualifiziert sein, wenn auf einen Typ in einem zugeordneten Xmlns beziehen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="a36cb-116">*TypeName* möglich ein anderen Typ als `typeof(object)`.</span><span class="sxs-lookup"><span data-stu-id="a36cb-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="a36cb-117">Die Factorymethode muss es sich um eine deklarierte öffentliche Methode des Typs sein, die die relevante Objektelement unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="a36cb-118">Die Factorymethode muss es sich um eine Instanz zurückgeben, die dem entsprechenden Objekt zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a36cb-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="a36cb-119">Factorymethoden sollte nie null zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a36cb-119">Factory methods should never return null.</span></span>  
  
 `x:Arguments` <span data-ttu-id="a36cb-120">Ein Prinzip der beste Übereinstimmung für Signaturen von Factorymethoden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a36cb-120">operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="a36cb-121">Abgleich wird die Anzahl der Parameter zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a36cb-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="a36cb-122">Gibt es ist mehr als eine mögliche Entsprechung für einen die Parameteranzahl, Parametertyp und dann ausgewertet und die beste Übereinstimmung bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="a36cb-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="a36cb-123">Wenn Mehrdeutigkeiten nach dieser Phase der Evaluierung noch vorhanden ist, ist die XAML-Prozessor-Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="a36cb-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="a36cb-124">Die `x:FactoryMethod` Objektelementverwendung ist nicht Eigenschaftselementverwendung im typischen Sinn, da das Markup-Direktive nicht der enthaltenden Objekt Typ des Elements verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a36cb-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="a36cb-125">Es wird davon ausgegangen, dass Elementverwendung wird seltener auf als die Verwendung von Attributen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-125">It is expected that element usage is less common than attribute usage.</span></span> `x:Arguments` <span data-ttu-id="a36cb-126">(entweder Attribut- oder Nutzung) kann verwendet werden, zusammen mit `x:FactoryMethod` Verwendung des Elements, aber dies wird nicht speziell angezeigt in den Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="a36cb-126">(either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 `x:FactoryMethod` <span data-ttu-id="a36cb-127">als ein Element mit allen anderen Eigenschaftenelemente stehen darf, müssen alle vorausgehen `x:Arguments` auch als Elemente angegeben, und muss alle Inhalt "oder" Inner Text/Initialisierungstext vor.</span><span class="sxs-lookup"><span data-stu-id="a36cb-127">as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36cb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a36cb-128">See also</span></span>

- [<span data-ttu-id="a36cb-129">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a36cb-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
