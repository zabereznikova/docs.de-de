---
title: Private, protected (C#-Referenz)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="37287-102">Private, protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="37287-102">private protected (C# Reference)</span></span>
<span data-ttu-id="37287-103">Die `private protected` schlüsselwortkombination wird der Zugriffsmodifizierer für einen Member.</span><span class="sxs-lookup"><span data-stu-id="37287-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="37287-104">Private geschützte Mitglied wird von Typen abgeleitet von der enthaltenden Klasse jedoch nur innerhalb der enthaltenden Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="37287-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="37287-105">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="37287-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="37287-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37287-106">Example</span></span>  
 <span data-ttu-id="37287-107">Ein privater, geschützter Member einer Basisklasse wird von abgeleiteten Typen in der enthaltenden Assembly zugegriffen werden kann, nur, wenn Sie der statische Typ der Variablen der abgeleiteten Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="37287-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="37287-108">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="37287-108">For example, consider the following code segment:</span></span>  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="37287-109">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="37287-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="37287-110">Die erste Datei enthält eine öffentliche Basisklasse `BaseClass`, und einen Typ abgeleitet wurde, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="37287-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="37287-111">`BaseClass`besitzt einen privaten geschützten Member `myValue`, welche `DerivedClass1` versucht, auf zwei Arten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="37287-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="37287-112">Der erste Versuch, den Zugriff auf `myValue` durch eine Instanz von `BaseClass` , löst einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="37287-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="37287-113">Allerdings der Versuch, ihn als einen geerbten Member in verwenden `DerivedClass1` wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37287-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="37287-114">In der zweiten Datei, einem versuchten Zugriff auf `myValue` als einen geerbten Member von `DerivedClass2` , löst einen Fehler, da nur von abgeleiteten Typen in Assembly1 möglich ist.</span><span class="sxs-lookup"><span data-stu-id="37287-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="37287-115">Strukturmember nicht `private protected` , da die Struktur nicht geerbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="37287-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="37287-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="37287-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37287-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37287-117">See Also</span></span>  
 <span data-ttu-id="37287-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="37287-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="37287-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="37287-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="37287-120">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="37287-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="37287-121">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="37287-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="37287-122">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="37287-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="37287-123">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="37287-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="37287-124">[Public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="37287-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="37287-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="37287-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="37287-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="37287-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="37287-127">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="37287-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
