---
title: internal – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: db653d0ed7f4835348484242b03392a8955c6392
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713429"
---
# <a name="internal-c-reference"></a><span data-ttu-id="affcf-102">internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="affcf-102">internal (C# Reference)</span></span>
<span data-ttu-id="affcf-103">Das Schlüsselwort `internal` ist ein [Zugriffsmodifizierer](./access-modifiers.md) für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="affcf-103">The `internal` keyword is an [access modifier](./access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="affcf-104">Auf dieser Seite wird der Zugriff auf `internal` behandelt.</span><span class="sxs-lookup"><span data-stu-id="affcf-104">This page covers `internal` access.</span></span> <span data-ttu-id="affcf-105">Das Schlüsselwort `internal` ist auch Teil des Zugriffsmodifizierers [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="affcf-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="affcf-106">Auf interne Typen oder Member kann nur innerhalb einer Datei in derselben Assembly zugegriffen werden, so wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="affcf-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 <span data-ttu-id="affcf-107">Einen Vergleich von `internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](./accessibility-levels.md) und [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="affcf-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](./accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="affcf-108">Weitere Informationen zu Assemblys finden Sie unter [Assemblys in .NET](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="affcf-108">For more information about assemblies, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
 <span data-ttu-id="affcf-109">Ein interner Zugriff wird häufig bei komponentenbasierten Entwicklungen verwendet, da auf diese Weise Gruppen von Komponenten privat kooperieren können, ohne dass sie für den Rest des Anwendungscodes verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="affcf-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="affcf-110">Ein Framework könnte z.B für das Erstellen grafischer Benutzeroberflächen `Control`- und `Form`-Klassen zur Verfügung stellen, die kooperieren, indem sie Member mit internen Zugriff verwenden.</span><span class="sxs-lookup"><span data-stu-id="affcf-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="affcf-111">Da diese Member intern sind, werden sie nicht für Code verfügbar gemacht, der das Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="affcf-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="affcf-112">Es ist unzulässig, auf einen Typen oder einen Member mit internem Zugriff außerhalb der Assembly zu verweisen, in der sie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="affcf-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="affcf-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affcf-113">Example</span></span>  
 <span data-ttu-id="affcf-114">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="affcf-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="affcf-115">Die erste Datei enthält eine interne Basisklasse, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="affcf-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="affcf-116">In der zweiten Datei führt der Versuch, `BaseClass` zu instanziieren zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="affcf-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="affcf-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affcf-117">Example</span></span>  
 <span data-ttu-id="affcf-118">Verwenden Sie in diesem Beispiel dieselbe Datei, die Sie im ersten Beispiel verwendet haben, und ändern Sie die Zugriffsebene von `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="affcf-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="affcf-119">Ändern Sie außerdem die Zugriffsebene des Members `intM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="affcf-119">Also change the accessibility level of the member `intM` to `internal`.</span></span> <span data-ttu-id="affcf-120">Jetzt können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="affcf-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="affcf-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="affcf-121">C# Language Specification</span></span>  

<span data-ttu-id="affcf-122">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="affcf-122">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="affcf-123">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="affcf-123">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="affcf-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="affcf-124">See also</span></span>

- [<span data-ttu-id="affcf-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="affcf-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="affcf-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="affcf-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="affcf-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="affcf-127">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="affcf-128">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="affcf-128">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="affcf-129">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="affcf-129">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="affcf-130">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="affcf-130">Modifiers</span></span>](index.md)
- [<span data-ttu-id="affcf-131">public</span><span class="sxs-lookup"><span data-stu-id="affcf-131">public</span></span>](./public.md)
- [<span data-ttu-id="affcf-132">private</span><span class="sxs-lookup"><span data-stu-id="affcf-132">private</span></span>](./private.md)
- [<span data-ttu-id="affcf-133">protected</span><span class="sxs-lookup"><span data-stu-id="affcf-133">protected</span></span>](./protected.md)
