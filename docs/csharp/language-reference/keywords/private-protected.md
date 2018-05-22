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
# <a name="private-protected-c-reference"></a>private protected (C#-Referenz)
Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member. Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly. Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Beispiel  
 Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist. Sehen Sie sich z.B. folgenden Codeabschnitt an:  
  
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
 Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`. Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`. `BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht. Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler. Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.
In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann. 

 Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.  
  
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
