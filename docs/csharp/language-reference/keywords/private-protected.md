---
title: private protected (C#-Referenz)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ee36cc713dd5fdb90ae20ef992f8e75eca09597d
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="c5dc3-102">private protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c5dc3-102">private protected (C# Reference)</span></span>
<span data-ttu-id="c5dc3-103">Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c5dc3-104">Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="c5dc3-105">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c5dc3-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="c5dc3-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5dc3-106">Example</span></span>  
 <span data-ttu-id="c5dc3-107">Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="c5dc3-108">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="c5dc3-108">For example, consider the following code segment:</span></span>  
  
 ```csharp
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
  
```csharp  
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
 <span data-ttu-id="c5dc3-109">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="c5dc3-110">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="c5dc3-111">`BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="c5dc3-112">Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="c5dc3-113">Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="c5dc3-114">In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="c5dc3-115">Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5dc3-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c5dc3-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c5dc3-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5dc3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5dc3-117">See Also</span></span>  
 <span data-ttu-id="c5dc3-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c5dc3-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c5dc3-120">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c5dc3-121">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="c5dc3-122">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="c5dc3-123">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="c5dc3-124">[Public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="c5dc3-125">[Private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="c5dc3-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="c5dc3-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="c5dc3-127">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="c5dc3-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
