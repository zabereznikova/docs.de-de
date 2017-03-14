---
title: "Einschr&#228;nkungen bei der Verwendung von Zugriffsebenen (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zugriffsmodifizierer [C#], Zugriffsebenenbeschränkungen"
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Einschr&#228;nkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)
Wenn Sie einen Typ in einer Deklaration angeben, überprüfen Sie, ob die Zugriffsebene des Typs von der Zugriffsebene eines Members oder eines anderen Typs abhängig ist.  So muss die direkte Basisklasse mindestens so zugreifbar sein wie die abgeleitete Klasse.  Die folgenden Deklarationen verursachen einen Compilerfehler, da die `BaseClass`\-Basisklasse weniger zugreifbar ist als `MyClass`:  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 Die nachstehende Tabelle fasst die Einschränkungen für deklarierte Zugriffsebenen zusammen.  
  
|Kontext|Hinweise|  
|-------------|--------------|  
|[Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)|Die direkte Basisklasse eines Klassentyps muss mindestens so zugreifbar sein wie der Klassentyp selbst.|  
|[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)|Die expliziten Basisschnittstellen eines Schnittstellentyps müssen mindestens so zugreifbar sein wie der Schnittstellentyp selbst.|  
|[Delegaten](../../../csharp/programming-guide/delegates/index.md)|Der Rückgabetyp und die Parametertypen eines Delegattyps müssen mindestens so zugreifbar sein wie der Delegattyp selbst.|  
|[Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)|Der Typ einer Konstante muss mindestens so zugreifbar sein wie die Konstante selbst.|  
|[Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)|Der Typ eines Felds muss mindestens so zugreifbar sein wie das Feld selbst.|  
|[Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)|Der Rückgabetyp und die Parametertypen einer Methode müssen mindestens so zugreifbar sein wie die Methode selbst.|  
|[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)|Der Typ einer Eigenschaft muss mindestens so zugreifbar sein wie die Eigenschaft selbst.|  
|[Ereignisse](../../../csharp/programming-guide/events/index.md)|Der Typ eines Ereignisses muss mindestens so zugreifbar sein wie das Ereignis selbst.|  
|[Indexer](../../../csharp/programming-guide/indexers/index.md)|Der Typ und die Parametertypen eines Indexers müssen mindestens so zugreifbar sein wie der Indexer selbst.|  
|[Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|Der Rückgabetyp und die Parametertypen eines Operators müssen mindestens so zugreifbar sein wie der Operator selbst.|  
|[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Die Parametertypen eines Konstruktors müssen mindestens so zugreifbar sein wie der Konstruktor selbst.|  
  
## Beispiel  
 Im folgenden Beispiel sind falsche Deklarationen verschiedener Typen enthalten.  Der einer Deklaration nachfolgende Kommentar zeigt den erwarteten Compilerfehler an.  
  
```  
// Restrictions on Using Accessibility Levels  
// CS0052 expected as well as CS0053, CS0056, and CS0057  
// To make the program work, change access level of both class B  
// and MyPrivateMethod() to public.  
  
using System;  
  
// A delegate:  
delegate int MyDelegate();  
  
class B  
{  
    // A private method:  
    static int MyPrivateMethod()  
    {  
        return 0;  
    }  
}  
  
public class A  
{  
    // Error: The type B is less accessible than the field A.myField.  
    public B myField = new B();  
  
    // Error: The type B is less accessible  
    // than the constant A.myConst.  
    public readonly B myConst = new B();  
  
    public B MyMethod()  
    {  
        // Error: The type B is less accessible   
        // than the method A.MyMethod.  
        return new B();  
    }  
  
    // Error: The type B is less accessible than the property A.MyProp  
    public B MyProp  
    {  
        set  
        {  
        }  
    }  
  
    MyDelegate d = new MyDelegate(B.MyPrivateMethod);  
    // Even when B is declared public, you still get the error:   
    // "The parameter B.MyPrivateMethod is not accessible due to   
    // protection level."  
  
    public static B operator +(A m1, B m2)  
    {  
        // Error: The type B is less accessible  
        // than the operator A.operator +(A,B)  
        return new B();  
    }  
  
    static void Main()  
    {  
        Console.Write("Compiled successfully");  
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
 [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [Private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)