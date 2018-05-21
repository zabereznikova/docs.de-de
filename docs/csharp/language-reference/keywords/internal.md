---
title: internal (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: d2fcc19bb7bc6de373412e7728f3025647c0435d
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="internal-c-reference"></a><span data-ttu-id="7c636-102">internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7c636-102">internal (C# Reference)</span></span>
<span data-ttu-id="7c636-103">Das Schlüsselwort `internal` ist ein [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="7c636-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="7c636-104">Auf dieser Seite wird der Zugriff auf `internal` behandelt.</span><span class="sxs-lookup"><span data-stu-id="7c636-104">This page covers `internal` access.</span></span> <span data-ttu-id="7c636-105">Das Schlüsselwort `internal` ist auch Teil des Zugriffsmodifizierers [`protected internal`](./protected-internal.md).</span><span class="sxs-lookup"><span data-stu-id="7c636-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="7c636-106">Auf interne Typen oder Member kann nur innerhalb einer Datei in derselben Assembly zugegriffen werden, so wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7c636-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="7c636-107">Einen Vergleich von `internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="7c636-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="7c636-108">Weitere Informationen zu Assemblys finden Sie unter [Assemblys und der globale Assemblycache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c636-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="7c636-109">Ein interner Zugriff wird häufig bei komponentenbasierten Entwicklungen verwendet, da auf diese Weise Gruppen von Komponenten privat kooperieren können, ohne dass sie für den Rest des Anwendungscodes verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7c636-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="7c636-110">Ein Framework könnte z.B für das Erstellen grafischer Benutzeroberflächen `Control`- und `Form`-Klassen zur Verfügung stellen, die kooperieren, indem sie Member mit internen Zugriff verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c636-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="7c636-111">Da diese Member intern sind, werden sie nicht für Code verfügbar gemacht, der das Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c636-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="7c636-112">Es ist unzulässig, auf einen Typen oder einen Member mit internem Zugriff außerhalb der Assembly zu verweisen, in der sie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7c636-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c636-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c636-113">Example</span></span>  
 <span data-ttu-id="7c636-114">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="7c636-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="7c636-115">Die erste Datei enthält eine interne Basisklasse, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="7c636-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="7c636-116">In der zweiten Datei führt der Versuch, `BaseClass` zu instanziieren zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="7c636-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
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
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="7c636-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c636-117">Example</span></span>  
 <span data-ttu-id="7c636-118">Verwenden Sie in diesem Beispiel dieselbe Datei, die Sie im ersten Beispiel verwendet haben, und ändern Sie die Zugriffsebene von `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="7c636-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="7c636-119">Ändern Sie außerdem die Zugriffsebene des Members `IntM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="7c636-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="7c636-120">Jetzt können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7c636-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
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
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="7c636-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="7c636-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c636-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c636-122">See Also</span></span>  
 [<span data-ttu-id="7c636-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7c636-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7c636-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7c636-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7c636-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7c636-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7c636-126">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="7c636-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="7c636-127">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="7c636-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="7c636-128">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="7c636-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="7c636-129">public</span><span class="sxs-lookup"><span data-stu-id="7c636-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="7c636-130">private</span><span class="sxs-lookup"><span data-stu-id="7c636-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="7c636-131">protected</span><span class="sxs-lookup"><span data-stu-id="7c636-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
