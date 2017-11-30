---
title: protected internal (C#-Referenz)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="e65e1-102">protected internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e65e1-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="e65e1-103">Die `protected internal` schlüsselwortkombination wird der Zugriffsmodifizierer für einen Member.</span><span class="sxs-lookup"><span data-stu-id="e65e1-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="e65e1-104">Ein geschützte interne Member ist zugegriffen werden kann, aus der aktuellen Assembly oder Typen, die von der enthaltenden Klasse abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="e65e1-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="e65e1-105">Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e65e1-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="e65e1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e65e1-106">Example</span></span>  
 <span data-ttu-id="e65e1-107">Ein interner geschützter Member einer Basisklasse ist von jedem Typ innerhalb der enthaltenden Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e65e1-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="e65e1-108">Es ist auch in einer abgeleiteten Klasse, die sich in einer anderen Assembly befindet, nur, wenn der Zugriff über eine Variable des Typs der abgeleiteten Klasse erfolgt, zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e65e1-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="e65e1-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="e65e1-109">For example, consider the following code segment:</span></span>  

```
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
  
```  
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
 <span data-ttu-id="e65e1-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="e65e1-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="e65e1-111">Die erste Datei enthält eine öffentliche Basisklasse `BaseClass`, und eine weitere Klasse `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="e65e1-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="e65e1-112">`BaseClass`einen geschützte interne Member besitzt `myValue`, die erfolgt durch die `TestAccess` Typ.</span><span class="sxs-lookup"><span data-stu-id="e65e1-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="e65e1-113">In der zweiten Datei, einem versuchten Zugriff auf `myValue` durch eine Instanz von `BaseClass` erzeugt einen Fehler beim Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e65e1-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="e65e1-114">Strukturmember nicht `protected internal` , da die Struktur nicht geerbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e65e1-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e65e1-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e65e1-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e65e1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e65e1-116">See Also</span></span>  
 <span data-ttu-id="e65e1-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e65e1-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e65e1-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e65e1-120">[Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="e65e1-121">[Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="e65e1-122">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="e65e1-123">[Public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="e65e1-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="e65e1-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="e65e1-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="e65e1-126">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="e65e1-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
