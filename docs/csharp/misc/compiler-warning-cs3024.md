---
title: Compilerwarnung CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 7515fdd7bc8f57890e3f1aac6303ed4607cc2249
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297292"
---
# <a name="compiler-warning-cs3024"></a>Compilerwarnung CS3024
Einschränkungstyp 'Typ' ist nicht CLS-kompatibel.  
  
 Der Compiler gibt diese Warnung aus, da die Verwendung eines nicht mit CLS-kompatiblen Typs als generische Typeinschränkung verhindern kann, dass Code, der in einigen Sprachen verfasst wurde, Ihre generische Klasse verwendet.  
  
### <a name="to-eliminate-this-warning"></a>So beseitigen Sie diese Warnung  
  
1. Verwenden Sie einen CLS-kompatiblen Typ für die Typeinschränkung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Fehler CS3024 an verschiedenen Stellen generiert:  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Einschränkungen für Typparameter](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
