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
# <a name="protected-internal-c-reference"></a>protected internal (C#-Referenz)
Die `protected internal` schlüsselwortkombination wird der Zugriffsmodifizierer für einen Member. Ein geschützte interne Member ist zugegriffen werden kann, aus der aktuellen Assembly oder Typen, die von der enthaltenden Klasse abgeleitet sind. Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Beispiel  
 Ein interner geschützter Member einer Basisklasse ist von jedem Typ innerhalb der enthaltenden Assembly zugegriffen werden kann. Es ist auch in einer abgeleiteten Klasse, die sich in einer anderen Assembly befindet, nur, wenn der Zugriff über eine Variable des Typs der abgeleiteten Klasse erfolgt, zugegriffen werden kann. Sehen Sie sich z.B. folgenden Codeabschnitt an:  

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
 Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`. Die erste Datei enthält eine öffentliche Basisklasse `BaseClass`, und eine weitere Klasse `TestAccess`. `BaseClass`einen geschützte interne Member besitzt `myValue`, die erfolgt durch die `TestAccess` Typ. In der zweiten Datei, einem versuchten Zugriff auf `myValue` durch eine Instanz von `BaseClass` erzeugt einen Fehler beim Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` wird erfolgreich ausgeführt. 

 Strukturmember nicht `protected internal` , da die Struktur nicht geerbt werden kann.  
  
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
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
