---
title: internal (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5674a78e2c317357c31d9e2661a25ce86cbf4f6a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="internal-c-reference"></a><span data-ttu-id="81a71-102">internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="81a71-102">internal (C# Reference)</span></span>
<span data-ttu-id="81a71-103">Das Schlüsselwort `internal` ist ein [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="81a71-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> <span data-ttu-id="81a71-104">Auf interne Typen oder Member kann nur innerhalb einer Datei in derselben Assembly zugegriffen werden, so wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="81a71-104">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 <span data-ttu-id="81a71-105">Auf Typen oder Member, die über den Zugriffsmodifizierer `protected internal` verfügen, kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="81a71-105">Types or members that have access modifier `protected internal` can be accessed from the current assembly or from types that are derived from the containing class.</span></span>  
  
 <span data-ttu-id="81a71-106">Einen Vergleich von `internal` mit dem anderen Zugriffsmodifizierer finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="81a71-106">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="81a71-107">Weitere Informationen zu Assemblys finden Sie unter [Assemblys und der globale Assemblycache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="81a71-107">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="81a71-108">Ein interner Zugriff wird häufig bei komponentenbasierten Entwicklungen verwendet, da auf diese Weise Gruppen von Komponenten privat kooperieren können, ohne dass sie für den Rest des Anwendungscodes verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="81a71-108">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="81a71-109">Ein Framework könnte z.B für das Erstellen grafischer Benutzeroberflächen `Control`- und `Form`-Klassen zur Verfügung stellen, die kooperieren, indem sie Member mit internen Zugriff verwenden.</span><span class="sxs-lookup"><span data-stu-id="81a71-109">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="81a71-110">Da diese Member intern sind, werden sie nicht für Code verfügbar gemacht, der das Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="81a71-110">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="81a71-111">Es ist unzulässig, auf einen Typen oder einen Member mit internem Zugriff außerhalb der Assembly zu verweisen, in der sie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="81a71-111">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81a71-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81a71-112">Example</span></span>  
 <span data-ttu-id="81a71-113">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly1_a.cs`.</span><span class="sxs-lookup"><span data-stu-id="81a71-113">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="81a71-114">Die erste Datei enthält eine interne Basisklasse, `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="81a71-114">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="81a71-115">In der zweiten Datei führt der Versuch, `BaseClass` zu instanziieren zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="81a71-115">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="81a71-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81a71-116">Example</span></span>  
 <span data-ttu-id="81a71-117">Verwenden Sie in diesem Beispiel dieselbe Datei, die Sie im ersten Beispiel verwendet haben, und ändern Sie die Zugriffsebene von `BaseClass` in `public`.</span><span class="sxs-lookup"><span data-stu-id="81a71-117">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="81a71-118">Ändern Sie außerdem die Zugriffsebene des Members `IntM` in `internal`.</span><span class="sxs-lookup"><span data-stu-id="81a71-118">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="81a71-119">Jetzt können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="81a71-119">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="81a71-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="81a71-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="81a71-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81a71-121">See Also</span></span>  
 <span data-ttu-id="81a71-122">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="81a71-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="81a71-124">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="81a71-125">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-125">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="81a71-126">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-126">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="81a71-127">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="81a71-128">[Public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-128">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="81a71-129">[Private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="81a71-129">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="81a71-130">protected</span><span class="sxs-lookup"><span data-stu-id="81a71-130">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

