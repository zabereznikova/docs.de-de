---
title: Compilerwarnung CS3024
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f175d102fa8a05b7f8c0a787564b933ff81cdf6c
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="compiler-warning-cs3024"></a>Compilerwarnung CS3024
Einschränkungstyp 'Typ' ist nicht CLS-kompatibel.  
  
 Der Compiler gibt diese Warnung aus, da die Verwendung eines nicht mit CLS-kompatiblen Typs als generische Typeinschränkung verhindern kann, dass Code, der in einigen Sprachen verfasst wurde, Ihre generische Klasse verwendet.  
  
### <a name="to-eliminate-this-warning"></a>So beseitigen Sie diese Warnung  
  
1.  Verwenden Sie einen CLS-kompatiblen Typ für die Typeinschränkung.  
  
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
 [Einschränkungen für Typparameter](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
