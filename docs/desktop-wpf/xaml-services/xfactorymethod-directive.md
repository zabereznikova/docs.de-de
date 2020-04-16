---
title: x:FactoryMethod-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432785"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="52b16-102">x:FactoryMethod-Anweisung</span><span class="sxs-lookup"><span data-stu-id="52b16-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="52b16-103">Gibt eine andere Methode als einen Konstruktor an, die ein XAML-Prozessor verwenden soll, um ein Objekt nach dem Auflösen seines Sicherungstyps zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="52b16-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="52b16-104">XAML-Attributverwendung, keine x:Argumente</span><span class="sxs-lookup"><span data-stu-id="52b16-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="52b16-105">XAML-Attributverwendung, x:Argumente als Element(e)</span><span class="sxs-lookup"><span data-stu-id="52b16-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="52b16-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="52b16-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="52b16-107">Der Zeichenfolgenmethodenname einer Methode, die XAML-Prozessoren `object`aufrufen, um die als angegebene Instanz zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="52b16-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="52b16-108">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="52b16-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="52b16-109">Ein oder mehrere Objektelemente für Objekte, die Factorymethodenparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="52b16-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="52b16-110">Ordnung ist bedeutend; Sie gibt die Reihenfolge an, in der Argumente an die Factory-Methode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52b16-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52b16-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="52b16-111">Remarks</span></span>  
 <span data-ttu-id="52b16-112">Wenn `methodname` es sich um eine Instanzmethode handelt, kann sie nicht qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="52b16-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="52b16-113">Statische Methoden als Factorymethoden werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52b16-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="52b16-114">Wenn `methodname` es sich `methodname` um eine `typeName.methodName` statische Methode `typeName` handelt, wird als Kombination bereitgestellt, wobei die Klasse, die die statische Factorymethode definiert, benennt wird.</span><span class="sxs-lookup"><span data-stu-id="52b16-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="52b16-115">`typeName`kann präfix-qualifiziert sein, wenn auf einen Typ in einem zugeordneten xmlns verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="52b16-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="52b16-116">`typeName`kann ein anderer `typeof(object)`Typ als sein.</span><span class="sxs-lookup"><span data-stu-id="52b16-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="52b16-117">Die Factorymethode muss eine deklarierte öffentliche Methode des Typs sein, der das relevante Objektelement unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52b16-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="52b16-118">Die Factorymethode muss eine Instanz zurückgeben, die dem relevanten Objekt zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="52b16-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="52b16-119">Factory-Methoden sollten niemals null zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="52b16-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="52b16-120">`x:Arguments`arbeitet nach dem Prinzip der besten Übereinstimmung für Die Signaturen von Fabrikmethoden.</span><span class="sxs-lookup"><span data-stu-id="52b16-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="52b16-121">Beim Matching wird zuerst die Parameteranzahl ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="52b16-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="52b16-122">Wenn es mehr als eine mögliche Übereinstimmung für eine Parameteranzahl gibt, wird der Parametertyp ausgewertet und die beste Übereinstimmung ermittelt.</span><span class="sxs-lookup"><span data-stu-id="52b16-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="52b16-123">Wenn nach dieser Phase der Evaluierung immer noch Mehrdeutigkeit enden ist, ist das XAML-Prozessorverhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="52b16-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="52b16-124">Die `x:FactoryMethod` Elementverwendung ist keine Eigenschaftselementverwendung im typischen Sinne, da das Direktivenmarkup nicht auf den Typ des enthaltenden Objektelements verweist.</span><span class="sxs-lookup"><span data-stu-id="52b16-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="52b16-125">Es wird erwartet, dass die Elementverwendung seltener ist als die Attributverwendung.</span><span class="sxs-lookup"><span data-stu-id="52b16-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="52b16-126">`x:Arguments`(entweder Attribut- oder Elementverwendung) `x:FactoryMethod` kann zusammen mit der Elementverwendung verwendet werden, dies wird jedoch nicht speziell in den Abschnitten Verwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52b16-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="52b16-127">`x:FactoryMethod`als Element muss vor allen anderen Eigenschaftselementen, `x:Arguments` muss vor allen auch als Elemente zur Verfügung gestellten und muss vor jedem Inhalt / inneren Text / Initialisierung Text vor.</span><span class="sxs-lookup"><span data-stu-id="52b16-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b16-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52b16-128">See also</span></span>

- [<span data-ttu-id="52b16-129">x:Arguments-Anweisung</span><span class="sxs-lookup"><span data-stu-id="52b16-129">x:Arguments Directive</span></span>](xarguments-directive.md)
