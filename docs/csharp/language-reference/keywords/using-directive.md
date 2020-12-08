---
description: using-Anweisung – C#-Referenz
title: using-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- using_CSharpKeyword
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 77d9c894dae9adc24343ce3a639a4afb904fb0a1
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599408"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="dc096-103">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dc096-103">using directive (C# Reference)</span></span>

<span data-ttu-id="dc096-104">Die `using`-Direktive hat drei Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="dc096-104">The `using` directive has three uses:</span></span>

- <span data-ttu-id="dc096-105">Sie ermöglicht die Verwendung von Typen in einem Namespace, sodass Sie die Verwendung eines Typs in diesem Namespace nicht qualifizieren müssen:</span><span class="sxs-lookup"><span data-stu-id="dc096-105">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>

    ```csharp
    using System.Text;
    ```

- <span data-ttu-id="dc096-106">Ermöglicht den Zugriff auf statische Member eines geschachtelten Typs, ohne den Zugriff mit dem Typnamen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="dc096-106">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span>

    ```csharp
    using static System.Math;
    ```

    <span data-ttu-id="dc096-107">Weitere Informationen finden Sie unter [using static-Direktive (C#-Referenz)](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="dc096-107">For more information, see the [using static directive](using-static.md).</span></span>

- <span data-ttu-id="dc096-108">Erstellen eines Alias für einen Namespace oder Typ.</span><span class="sxs-lookup"><span data-stu-id="dc096-108">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="dc096-109">Dies wird als *using-Aliasdirektive* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dc096-109">This is called a *using alias directive*.</span></span>

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

<span data-ttu-id="dc096-110">Das `using`-Schlüsselwort wird auch zum Erstellen von *using-Anweisungen* verwendet, mit denen sichergestellt wird, dass <xref:System.IDisposable>-Objekte wie Dateien und Schriftarten richtig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dc096-110">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="dc096-111">Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dc096-111">See [using Statement](using-statement.md) for more information.</span></span>

## <a name="using-static-type"></a><span data-ttu-id="dc096-112">Verwenden statischer Typen</span><span class="sxs-lookup"><span data-stu-id="dc096-112">Using static type</span></span>

<span data-ttu-id="dc096-113">Sie können auf statische Member eines Typs zugreifen, ohne den Zugriff mit dem Typnamen zu qualifizieren:</span><span class="sxs-lookup"><span data-stu-id="dc096-113">You can access static members of a type without having to qualify the access with the type name:</span></span>

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a><span data-ttu-id="dc096-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dc096-114">Remarks</span></span>

<span data-ttu-id="dc096-115">Der Bereich einer `using`-Direktive ist auf die Datei beschränkt, in der er enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dc096-115">The scope of a `using` directive is limited to the file in which it appears.</span></span>

<span data-ttu-id="dc096-116">Die `using`-Direktive kann an folgenden Stellen erscheinen:</span><span class="sxs-lookup"><span data-stu-id="dc096-116">The `using` directive can appear:</span></span>

- <span data-ttu-id="dc096-117">Am Anfang einer Quellcodedatei, vor Namespace- oder Typdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="dc096-117">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="dc096-118">In einem beliebigen Namespace, jedoch vor in diesem Namespace deklarierten Namespaces oder Typen.</span><span class="sxs-lookup"><span data-stu-id="dc096-118">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="dc096-119">Andernfalls wird der Compilerfehler [CS1529](../../misc/cs1529.md) generiert.</span><span class="sxs-lookup"><span data-stu-id="dc096-119">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>

<span data-ttu-id="dc096-120">Erstellen Sie eine `using`-Alias-Direktive, um das Qualifizieren eines Bezeichners in einen Namespace oder Typ zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="dc096-120">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="dc096-121">In jeder `using`-Direktive muss der vollqualifizierte Namespace oder Typ unabhängig von den davor aufgeführten `using`-Direktiven verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc096-121">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="dc096-122">In der Deklaration einer `using`-Direktive kann kein `using`-Alias verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc096-122">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="dc096-123">Der folgende Code verursacht beispielsweise einen Compilerfehler:</span><span class="sxs-lookup"><span data-stu-id="dc096-123">For example, the following generates a compiler error:</span></span>

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

<span data-ttu-id="dc096-124">Erstellen Sie eine `using`-Direktive, um die Typen in einem Namespace zu verwenden, ohne den Namespace angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="dc096-124">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="dc096-125">Eine `using`-Direktive ermöglicht Ihnen nicht den Zugriff auf Namespaces, die im angegebenen Namespace geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="dc096-125">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>

<span data-ttu-id="dc096-126">Gibt zwei Kategorien von Namespaces: benutzerdefinierte und systemdefinierte Namespaces.</span><span class="sxs-lookup"><span data-stu-id="dc096-126">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="dc096-127">Benutzerdefinierte Namespaces sind Namespaces, die im Code definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dc096-127">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="dc096-128">Eine Liste der systemdefinierten Namespaces finden Sie unter [.NET API-Browser](../../../../api/index.md).</span><span class="sxs-lookup"><span data-stu-id="dc096-128">For a list of the system-defined namespaces, see [.NET API Browser](../../../../api/index.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="dc096-129">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="dc096-129">Example 1</span></span>

<span data-ttu-id="dc096-130">Das folgende Beispiel zeigt, wie Sie einen `using`-Alias für einen Namespace definieren und verwenden:</span><span class="sxs-lookup"><span data-stu-id="dc096-130">The following example shows how to define and use a `using` alias for a namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

<span data-ttu-id="dc096-131">Eine using-Aliasanweisung kann auf der rechten Seite nicht über einen offenen generischen Typen verfügen.</span><span class="sxs-lookup"><span data-stu-id="dc096-131">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="dc096-132">Sie können zum Beispiel keinen using-Alias für `List<T>` erstellen, jedoch für `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="dc096-132">For example, you cannot create a using alias for a `List<T>`, but you can create one for a `List<int>`.</span></span>

## <a name="example-2"></a><span data-ttu-id="dc096-133">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="dc096-133">Example 2</span></span>

<span data-ttu-id="dc096-134">Das folgende Beispiel zeigt, wie Sie eine `using`-Direktive und einen `using`-Alias für eine Klasse definieren:</span><span class="sxs-lookup"><span data-stu-id="dc096-134">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="dc096-135">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="dc096-135">C# language specification</span></span>

<span data-ttu-id="dc096-136">Weitere Informationen finden Sie unter [using-Direktiven](~/_csharplang/spec/namespaces.md#using-directives) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="dc096-136">For more information, see [Using directives](~/_csharplang/spec/namespaces.md#using-directives) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="dc096-137">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="dc096-137">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc096-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc096-138">See also</span></span>

- [<span data-ttu-id="dc096-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dc096-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc096-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dc096-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc096-141">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="dc096-141">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="dc096-142">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dc096-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dc096-143">Namespaces</span><span class="sxs-lookup"><span data-stu-id="dc096-143">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
- [<span data-ttu-id="dc096-144">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dc096-144">using Statement</span></span>](using-statement.md)
