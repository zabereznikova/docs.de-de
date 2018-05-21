---
title: protected internal (C#-Referenz)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="dd983-102">protected internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dd983-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="dd983-103">Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="dd983-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="dd983-104">Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="dd983-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="dd983-105">Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="dd983-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="dd983-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd983-106">Example</span></span>  
 <span data-ttu-id="dd983-107">Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="dd983-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="dd983-108">Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt.</span><span class="sxs-lookup"><span data-stu-id="dd983-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="dd983-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="dd983-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```csharp  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 <span data-ttu-id="dd983-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="dd983-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="dd983-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="dd983-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="dd983-112">`BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="dd983-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="dd983-113">In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt.</span><span class="sxs-lookup"><span data-stu-id="dd983-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="dd983-114">Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd983-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd983-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dd983-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd983-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd983-116">See Also</span></span>  
 <span data-ttu-id="dd983-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dd983-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dd983-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="dd983-120">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="dd983-121">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="dd983-122">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="dd983-123">[Public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="dd983-124">[Private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="dd983-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="dd983-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="dd983-126">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="dd983-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
