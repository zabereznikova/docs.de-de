---
title: internal (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: 54ec003683953b53dedf8885a41350daf5338f83
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523360"
---
# <a name="internal-c-reference"></a>internal (C#-Referenz)
Das Schlüsselwort `internal` ist ein [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) für Typen und Typmember. 
  
 > Auf dieser Seite wird der Zugriff auf `internal` behandelt. Das Schlüsselwort `internal` ist auch Teil des Zugriffsmodifizierers [`protected internal`](./protected-internal.md).
  
Auf interne Typen oder Member kann nur innerhalb einer Datei in derselben Assembly zugegriffen werden, so wie in diesem Beispiel:  
  
```csharp  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 Einen Vergleich von `internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Weitere Informationen zu Assemblys finden Sie unter [Assemblys und der globale Assemblycache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).  
  
 Ein interner Zugriff wird häufig bei komponentenbasierten Entwicklungen verwendet, da auf diese Weise Gruppen von Komponenten privat kooperieren können, ohne dass sie für den Rest des Anwendungscodes verfügbar gemacht werden. Ein Framework könnte z.B für das Erstellen grafischer Benutzeroberflächen `Control`- und `Form`-Klassen zur Verfügung stellen, die kooperieren, indem sie Member mit internen Zugriff verwenden. Da diese Member intern sind, werden sie nicht für Code verfügbar gemacht, der das Framework verwendet.  
  
 Es ist unzulässig, auf einen Typen oder einen Member mit internem Zugriff außerhalb der Assembly zu verweisen, in der sie definiert wurden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly1_a.cs`. Die erste Datei enthält eine interne Basisklasse, `BaseClass`. In der zweiten Datei führt der Versuch, `BaseClass` zu instanziieren zu einem Fehler.  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie in diesem Beispiel dieselbe Datei, die Sie im ersten Beispiel verwendet haben, und ändern Sie die Zugriffsebene von `BaseClass` in `public`. Ändern Sie außerdem die Zugriffsebene des Members `IntM` in `internal`. Jetzt können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)  
- [public](../../../csharp/language-reference/keywords/public.md)  
- [private](../../../csharp/language-reference/keywords/private.md)  
- [protected](../../../csharp/language-reference/keywords/protected.md)
