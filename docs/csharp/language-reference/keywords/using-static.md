---
title: using static-Direktive (C#-Referenz)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5838bede475cf2ad1b72518770241e86206a06bb
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="e1d9d-102">using static-Direktive (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e1d9d-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="e1d9d-103">Die `using static`-Direktive legt einen Typ fest, auf dessen statische Member Sie ohne Angabe eines Typnamens zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="e1d9d-104">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="e1d9d-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="e1d9d-105">Wo *vollqualifizierter Typname* der Name des Typs ist, auf dessen statische Member verwiesen werden kann, ohne einen Typnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="e1d9d-106">Wenn Sie keinen vollqualifizierten Typnamen angeben (der vollständige Namespacename mit dem Typnamen), generiert C# den Compilerfehler CS0246: „The type or namespace name '<type-name>' could not be found“ („Der Typ- oder Namespacename <type-name> konnte nicht gefunden werden.“)</span><span class="sxs-lookup"><span data-stu-id="e1d9d-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="e1d9d-107">Die `using static`-Direktive gilt für jeden Typ, der über statische Member verfügt, auch wenn er ebenfalls über Instanzmember verfügt.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="e1d9d-108">Instanzmember können jedoch nur über die Typinstanz aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="e1d9d-109">Die `using static`-Direktive wurde in C# 6 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1d9d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1d9d-110">Remarks</span></span>
 
<span data-ttu-id="e1d9d-111">Wenn Sie einen statischen Member aufrufen, geben Sie normalerweise den Typnamen zusammen mit dem Membernamen an.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="e1d9d-112">Das wiederholte Eingeben desselben Typnamens zum Aufrufen von Membern dieses Typs kann zu ausführlichem, verwirrendem Code führen.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="e1d9d-113">Die folgende Definition einer `Circle`-Klasse verweist z.B. auf mehrere Member der Klasse <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>
  
[!code-csharp[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="e1d9d-114">Da nicht mehr jedes Mal explizit auf die Klasse <xref:System.Math> verwiesen werden muss, wenn auf einen Member verwiesen wird, erzeugt die `using static`-Direktive deutlich übersichtlicheren Code:</span><span class="sxs-lookup"><span data-stu-id="e1d9d-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="e1d9d-115">`using static` importiert nur zugängliche statische Member und geschachtelte Typen, die im angegebenen Typ deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="e1d9d-116">Geerbte Member werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-116">Inherited members are not imported.</span></span>  <span data-ttu-id="e1d9d-117">Sie können aus jedem benannten Typen mit einer statischen using-Anweisung importieren, einschließlich Visual Basic-Module.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="e1d9d-118">Wenn F#-Funktionen der obersten Ebene in den Metadaten als statische Member eines benannten Typs angezeigt werden, dessen Name ein gültiger C#-Bezeichner ist, können die F#-Funktionen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="e1d9d-119">`using static` macht Erweiterungsmethoden, die im angegebenen Typ deklariert sind, für die Erweiterungsmethodensuche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="e1d9d-120">Die Namen der Erweiterungsmethoden werden jedoch bei nicht referenzierten Verweisen im Code nicht in den Bereich importiert.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="e1d9d-121">Methoden mit dem gleichen Namen, die aus verschiedenen Typen von verschiedenen statischen `using static`-Direktiven in der gleichen Kompilierungseinheit oder dem gleichen Namespace importiert wurden, bilden eine Methodengruppe.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="e1d9d-122">Die Überladungsauflösung innerhalb dieser Methodengruppen folgt den normalen C#-Regeln.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-122">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1d9d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1d9d-123">Example</span></span>

<span data-ttu-id="e1d9d-124">Im folgenden Beispiele wird die `using static`-Direktive verwendet, um die statischen Member der Klassen <xref:System.Console>, <xref:System.Math> und <xref:System.String> zugänglich zu machen, ohne deren Typnamen angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="e1d9d-125">In diesem Beispiel hätte die `using static`-Direktive auch auf den Typ <xref:System.Double> angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="e1d9d-126">Dies gewesen wäre es möglich ist, rufen Sie die <xref:System.Double.TryParse(System.String,System.Double@)> Methode ohne ein Typname.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="e1d9d-127">Hierdurch wird allerdings weniger lesbarer Code generiert, da die `using static`-Anweisungen überprüft werden müssen, um zu bestimmen, welche `TryParse`-Methode eines numerischen Typs aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e1d9d-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1d9d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1d9d-128">See also</span></span>

<span data-ttu-id="e1d9d-129">[using directive (using-Direktive)](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="e1d9d-129">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="e1d9d-130">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e1d9d-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="e1d9d-131">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e1d9d-131">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="e1d9d-132">[Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="e1d9d-132">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="e1d9d-133">[Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e1d9d-133">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="e1d9d-134">Namespaces</span><span class="sxs-lookup"><span data-stu-id="e1d9d-134">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   
