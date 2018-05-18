---
title: protected internal (C#-Referenz)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: a2a649f0fdb924c26380e7261bd935be736f0665
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="protected-internal-c-reference"></a>protected internal (C#-Referenz)
Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member. Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden. Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Beispiel  
 Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden. Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt. Sehen Sie sich z.B. folgenden Codeabschnitt an:  

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
 Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`. Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`. `BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird. In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt. 

 Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Public](../../../csharp/language-reference/keywords/public.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
