---
title: using static-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fa8dc3c043665ca2f56facf516cb03e5c6bb9d7
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421758"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="f51e5-102">using static-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f51e5-102">using static directive (C# Reference)</span></span>

<span data-ttu-id="f51e5-103">Die `using static`-Anweisung legt einen Typ fest, auf dessen statische Member und geschachtelte Typen Sie ohne Angabe eines Typnamens zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f51e5-103">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="f51e5-104">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="f51e5-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="f51e5-105">Hier steht *fully-qualified-type-name* für den Namen des Typs, auf dessen statische Member und geschachtelte Typen verwiesen werden kann, ohne einen Typnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f51e5-105">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="f51e5-106">Wenn Sie keinen vollqualifizierten Typnamen angeben (der vollständige Namespacename zusammen mit dem Typnamen), generiert C# den Compilerfehler [CS0246](../compiler-messages/cs0246.md): Der Typ- oder Namespacename "type/namespace" konnte nicht gefunden werden (fehlt eine using-Direktive oder ein Assemblyverweis?).</span><span class="sxs-lookup"><span data-stu-id="f51e5-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="f51e5-107">Die `using static`-Anweisung gilt für jeden Typ, der über statische Member (oder geschachtelte Typen) verfügt, auch wenn er ebenfalls über Instanzmember verfügt.</span><span class="sxs-lookup"><span data-stu-id="f51e5-107">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="f51e5-108">Instanzmember können jedoch nur über die Typinstanz aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f51e5-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="f51e5-109">Die `using static`-Direktive wurde in C# 6 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f51e5-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="f51e5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f51e5-110">Remarks</span></span>

<span data-ttu-id="f51e5-111">Wenn Sie einen statischen Member aufrufen, geben Sie normalerweise den Typnamen zusammen mit dem Membernamen an.</span><span class="sxs-lookup"><span data-stu-id="f51e5-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="f51e5-112">Das wiederholte Eingeben desselben Typnamens zum Aufrufen von Membern dieses Typs kann zu ausführlichem, verwirrendem Code führen.</span><span class="sxs-lookup"><span data-stu-id="f51e5-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="f51e5-113">Die folgende Definition einer `Circle`-Klasse verweist z.B. auf mehrere Member der Klasse <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="f51e5-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="f51e5-114">Da nicht mehr jedes Mal explizit auf die Klasse <xref:System.Math> verwiesen werden muss, wenn auf einen Member verwiesen wird, erzeugt die `using static`-Direktive deutlich übersichtlicheren Code:</span><span class="sxs-lookup"><span data-stu-id="f51e5-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="f51e5-115">`using static` importiert nur zugängliche statische Member und geschachtelte Typen, die im angegebenen Typ deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="f51e5-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="f51e5-116">Geerbte Member werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="f51e5-116">Inherited members are not imported.</span></span>  <span data-ttu-id="f51e5-117">Sie können aus jedem benannten Typen mit einer statischen using-Anweisung importieren, einschließlich Visual Basic-Module.</span><span class="sxs-lookup"><span data-stu-id="f51e5-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="f51e5-118">Wenn F#-Funktionen der obersten Ebene in den Metadaten als statische Member eines benannten Typs angezeigt werden, dessen Name ein gültiger C#-Bezeichner ist, können die F#-Funktionen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="f51e5-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="f51e5-119">`using static` macht Erweiterungsmethoden, die im angegebenen Typ deklariert sind, für die Erweiterungsmethodensuche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f51e5-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="f51e5-120">Die Namen der Erweiterungsmethoden werden jedoch bei nicht referenzierten Verweisen im Code nicht in den Bereich importiert.</span><span class="sxs-lookup"><span data-stu-id="f51e5-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="f51e5-121">Methoden mit dem gleichen Namen, die aus verschiedenen Typen von verschiedenen statischen `using static`-Direktiven in der gleichen Kompilierungseinheit oder dem gleichen Namespace importiert wurden, bilden eine Methodengruppe.</span><span class="sxs-lookup"><span data-stu-id="f51e5-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="f51e5-122">Die Überladungsauflösung innerhalb dieser Methodengruppen folgt den normalen C#-Regeln.</span><span class="sxs-lookup"><span data-stu-id="f51e5-122">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="f51e5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f51e5-123">Example</span></span>

<span data-ttu-id="f51e5-124">Im folgenden Beispiele wird die `using static`-Direktive verwendet, um die statischen Member der Klassen <xref:System.Console>, <xref:System.Math> und <xref:System.String> zugänglich zu machen, ohne deren Typnamen angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f51e5-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="f51e5-125">In diesem Beispiel hätte die `using static`-Direktive auch auf den Typ <xref:System.Double> angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f51e5-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="f51e5-126">Dadurch wäre es möglich geworden, die Methode <xref:System.Double.TryParse(System.String,System.Double@)> aufzurufen, ohne einen Typnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f51e5-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="f51e5-127">Hierdurch wird allerdings weniger lesbarer Code generiert, da die `using static`-Anweisungen überprüft werden müssen, um zu bestimmen, welche `TryParse`-Methode eines numerischen Typs aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f51e5-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="f51e5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f51e5-128">See also</span></span>

- [<span data-ttu-id="f51e5-129">using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f51e5-129">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="f51e5-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f51e5-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f51e5-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f51e5-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f51e5-132">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="f51e5-132">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="f51e5-133">Namespaces</span><span class="sxs-lookup"><span data-stu-id="f51e5-133">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
