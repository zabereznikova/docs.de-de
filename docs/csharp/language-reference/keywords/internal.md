---
title: "internal (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "internal_CSharpKeyword"
  - "internal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "internal-Schlüsselwort [C#]"
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# internal (C#-Referenz)
Das `internal`\-Schlüsselwort ist [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) für Typen und Typmember.  Auf interne Typen oder Member kann nur in Dateien derselben Assembly zugegriffen werden, wie dieses Beispiel zeigt:  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 Auf Typen oder Member, die über `protected internal`\-Zugriffsmodifizierer verfügen, kann von der aktuellen Assembly oder von den Typen zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.  
  
 Einen Vergleich von `internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Weitere Informationen zu Assemblys finden Sie unter [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Der interne Zugriff wird häufig in komponentenbasierter Entwicklung verwendet, da er einer Gruppe von Komponenten ermöglicht, in einer nicht öffentlichen Weise zusammenzuwirken, ohne dem Rest des Anwendungscodes zugänglich zu sein.  Ein Framework zum Erstellen von grafischen Benutzeroberflächen kann beispielsweise die `Control`\-Klasse und die `Form`\-Klasse bereitstellen, die unter Verwendung von Membern mit internem Zugriff zusammenwirken.  Da es sich bei diesen Membern um interne Elemente handelt, sind sie nicht dem Code, der das Gerüst verwendet, zugänglich gemacht worden.  
  
 Außerhalb der Assembly, in der ein Typ oder Member mit internem Zugriff definiert wurde, darf nicht auf diesen verwiesen werden.  
  
## Beispiel  
 In diesem Beispiel sind zwei Dateien enthalten, `Assembly1.cs` und `Assembly1`\_`a.cs`.  Die erste Datei weist eine interne Basisklasse auf, `BaseClass`.  In der zweiten Datei erzeugt ein Versuch, `BaseClass` zu instanziieren, einen Fehler.  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
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
  
## Beispiel  
 Verwenden Sie in diesem Beispiel dieselben Dateien wie in Beispiel 1, und ändern Sie die Zugriffsebene von `BaseClass` in `public`.  Ändern Sie außerdem die Zugriffsebene des Members `IntM` auf `internal`.  In diesem Fall können Sie die Klasse instanziieren, aber Sie können nicht auf den internen Member zugreifen.  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)