---
title: Compilerwarnung CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 6147fc1aafc06d7c844cfc39eafebbd737d89610
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69601959"
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="4ff82-102">Compilerwarnung CS3024</span><span class="sxs-lookup"><span data-stu-id="4ff82-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="4ff82-103">Einschränkungstyp 'Typ' ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="4ff82-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="4ff82-104">Der Compiler gibt diese Warnung aus, da die Verwendung eines nicht mit CLS-kompatiblen Typs als generische Typeinschränkung verhindern kann, dass Code, der in einigen Sprachen verfasst wurde, Ihre generische Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ff82-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="4ff82-105">So beseitigen Sie diese Warnung</span><span class="sxs-lookup"><span data-stu-id="4ff82-105">To eliminate this warning</span></span>  
  
1. <span data-ttu-id="4ff82-106">Verwenden Sie einen CLS-kompatiblen Typ für die Typeinschränkung.</span><span class="sxs-lookup"><span data-stu-id="4ff82-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ff82-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ff82-107">Example</span></span>  
 <span data-ttu-id="4ff82-108">Im folgenden Beispiel wird der Fehler CS3024 an verschiedenen Stellen generiert:</span><span class="sxs-lookup"><span data-stu-id="4ff82-108">The following example generates CS3024 in several locations:</span></span>  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ff82-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ff82-109">See also</span></span>

- [<span data-ttu-id="4ff82-110">Einschränkungen für Typparameter</span><span class="sxs-lookup"><span data-stu-id="4ff82-110">Constraints on Type Parameters</span></span>](../programming-guide/generics/constraints-on-type-parameters.md)
