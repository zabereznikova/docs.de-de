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
# <a name="private-protected-c-reference"></a>Private, protected (C#-Referenz)
Die `private protected` schlüsselwortkombination wird der Zugriffsmodifizierer für einen Member. Private geschützte Mitglied wird von Typen abgeleitet von der enthaltenden Klasse jedoch nur innerhalb der enthaltenden Assembly zugegriffen werden kann. Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Beispiel  
 Ein privater, geschützter Member einer Basisklasse wird von abgeleiteten Typen in der enthaltenden Assembly zugegriffen werden kann, nur, wenn Sie der statische Typ der Variablen der abgeleiteten Klassentyp ist. Sehen Sie sich z.B. folgenden Codeabschnitt an:  
  
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
 Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`. Die erste Datei enthält eine öffentliche Basisklasse `BaseClass`, und einen Typ abgeleitet wurde, `DerivedClass1`. `BaseClass`besitzt einen privaten geschützten Member `myValue`, welche `DerivedClass1` versucht, auf zwei Arten zugreifen. Der erste Versuch, den Zugriff auf `myValue` durch eine Instanz von `BaseClass` , löst einen Fehler. Allerdings der Versuch, ihn als einen geerbten Member in verwenden `DerivedClass1` wird erfolgreich ausgeführt.
In der zweiten Datei, einem versuchten Zugriff auf `myValue` als einen geerbten Member von `DerivedClass2` , löst einen Fehler, da nur von abgeleiteten Typen in Assembly1 möglich ist. 

 Strukturmember nicht `private protected` , da die Struktur nicht geerbt werden kann.  
  
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
