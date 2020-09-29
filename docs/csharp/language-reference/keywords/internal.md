---
description: internal – C#-Referenz
title: internal – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: c66f4ff578e9864ebaf2b89ec03ce95f3cb2ba91
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168737"
---
# <a name="internal-c-reference"></a><span data-ttu-id="02585-103">internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="02585-103">internal (C# Reference)</span></span>

<span data-ttu-id="02585-104">Das Schlüsselwort `internal` ist ein [Zugriffsmodifizierer](./access-modifiers.md) für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="02585-104">The `internal` keyword is an [access modifier](./access-modifiers.md) for types and type members.</span></span>
  
 > <span data-ttu-id="02585-105">Auf dieser Seite wird der Zugriff auf `internal` behandelt.</span><span class="sxs-lookup"><span data-stu-id="02585-105">This page covers `internal` access.</span></span> <span data-ttu-id="02585-106">Das Schlüsselwort `internal` ist auch Teil des Zugriffsmodifizierers [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="02585-106">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="02585-107">Auf interne Typen oder Member kann nur innerhalb einer Datei in derselben Assembly zugegriffen werden, so wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="02585-107">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 <span data-ttu-id="02585-108">Einen Vergleich von `internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](./accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="02585-108">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](./accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="02585-109">Weitere Informationen zu Assemblys finden Sie unter [Assemblys in .NET](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="02585-109">For more information about assemblies, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
 <span data-ttu-id="02585-110">Ein interner Zugriff wird häufig bei komponentenbasierten Entwicklungen verwendet, da auf diese Weise Gruppen von Komponenten privat kooperieren können, ohne dass sie für den Rest des Anwendungscodes verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="02585-110">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="02585-111">Ein Framework könnte z.B für das Erstellen grafischer Benutzeroberflächen `Control`- und `Form`-Klassen zur Verfügung stellen, die kooperieren, indem sie Member mit internen Zugriff verwenden.</span><span class="sxs-lookup"><span data-stu-id="02585-111">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="02585-112">Da diese Member intern sind, werden sie nicht für Code verfügbar gemacht, der das Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="02585-112">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="02585-113">Es ist unzulässig, auf einen Typen oder einen Member mit internem Zugriff außerhalb der Assembly zu verweisen, in der sie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="02585-113">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02585-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02585-114">Example</span></span>  

 <span data-ttu-id="02585-115">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="02585-115">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="02585-116">Die erste Datei enthält eine interne Basisklasse, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="02585-116">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="02585-117">In der zweiten Datei führt der Versuch, `BaseClass` zu instanziieren zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="02585-117">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="02585-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02585-118">Example</span></span>  

 <span data-ttu-id="02585-119">Verwenden Sie in diesem Beispiel dieselbe Datei, die Sie im ersten Beispiel verwendet haben, und ändern Sie die Zugriffsebene von `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="02585-119">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="02585-120">Ändern Sie außerdem die Zugriffsebene des Members `intM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="02585-120">Also change the accessibility level of the member `intM` to `internal`.</span></span> <span data-ttu-id="02585-121">Jetzt können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="02585-121">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="02585-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="02585-122">C# Language Specification</span></span>  

<span data-ttu-id="02585-123">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="02585-123">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="02585-124">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="02585-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02585-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02585-125">See also</span></span>

- [<span data-ttu-id="02585-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="02585-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02585-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="02585-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02585-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="02585-128">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="02585-129">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="02585-129">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="02585-130">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="02585-130">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="02585-131">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="02585-131">Modifiers</span></span>](index.md)
- [<span data-ttu-id="02585-132">public</span><span class="sxs-lookup"><span data-stu-id="02585-132">public</span></span>](./public.md)
- [<span data-ttu-id="02585-133">private</span><span class="sxs-lookup"><span data-stu-id="02585-133">private</span></span>](./private.md)
- [<span data-ttu-id="02585-134">protected</span><span class="sxs-lookup"><span data-stu-id="02585-134">protected</span></span>](./protected.md)
