---
title: "Zeigertypen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeiger [C#]"
  - "Unsicherer Code [C#], Zeiger"
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Zeigertypen (C#-Programmierhandbuch)
In einem unsicheren Kontext kann ein Typ sowohl ein Zeigertyp als auch ein Werttyp oder Verweistyp sein.  Eine Zeigertypdeklaration erfolgt in einer der folgenden Formen:  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 Die folgenden Typen können Zeigertypen sein:  
  
-   [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) oder [bool](../../../csharp/language-reference/keywords/bool.md).  
  
-   Beliebiger [enum](../../../csharp/language-reference/keywords/enum.md)\-Typ.  
  
-   Beliebiger Zeigertyp.  
  
-   Beliebiger benutzerdefinierter Strukturtyp, der nur Felder von nicht verwalteten Typen enthält.  
  
 Zeigertypen erben nicht von [object](../../../csharp/language-reference/keywords/object.md), und es ist keine Konvertierung zwischen Zeigertypen und `object` möglich.  Weiterhin unterstützen Boxing und Unboxing keine Zeiger.  Es ist jedoch möglich, Konvertierungen zwischen verschiedenen Zeigertypen sowie zwischen Zeigertypen und ganzzahligen Typen durchzuführen.  
  
 Wenn Sie mehrere Zeiger innerhalb ein\- und derselben Deklaration deklarieren, wird das Sternchen \(\*\) nur einmal mit dem zugrunde liegenden Typ notiert und nicht als Präfix für jeden Zeigernamen verwendet.  Beispiel:  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 Ein Zeiger kann nicht auf einen Verweis oder eine [Struktur](../../../csharp/language-reference/keywords/struct.md) verweisen, die Verweise enthält, da ein Objektverweis auch dann in die Garbage Collection aufgenommen werden kann, wenn ein Zeiger darauf verweist.  In der Garbage Collection wird nicht nachgehalten, ob von einem der Zeigertypen auf ein Objekt verwiesen wird.  
  
 Der Wert der Zeigervariablen vom Typ `myType*` ist die Adresse einer Variablen vom Typ `myType`.  Im Folgenden finden Sie Beispiele für Zeigertypdeklarationen:  
  
|Beispiel|Beschreibung|  
|--------------|------------------|  
|`int* p`|`p` ist ein Zeiger auf einen ganzzahligen Wert.|  
|`int** p`|`p` ist ein Zeiger auf einen Zeiger auf einen ganzzahligen Wert.|  
|`int*[] p`|`p` ist ein eindimensionales Array von Zeigern auf ganzzahlige Werte.|  
|`char* p`|`p` ist ein Zeiger auf eine char\-Variable.|  
|`void* p`|`p` ist ein Zeiger auf einen unbekannten Typ.|  
  
 Sie können den Zeigerdereferenzierungsoperator \* verwenden, um auf den Inhalt an der Speicherstelle zuzugreifen, auf die die Zeigervariable zeigt.  Betrachten Sie beispielsweise die folgende Deklaration:  
  
```  
int* myVariable;  
```  
  
 Der Ausdruck `*myVariable` kennzeichnet die `int`\-Variable, die sich an der in `myVariable` enthaltenen Adresse befindet.  
  
 Es gibt mehrere Beispiele von Zeigern in den Themen [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) und [Zeigerkonvertierungen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).  Im folgenden Beispiel wird die Notwendigkeit für das `unsafe`\-Schlüsselwort und die `fixed`\-Anweisung sowie die Vorgehensweise zum Erhöhen eines inneren Zeigers veranschaulicht.  Sie können diesen Code in die Hauptmethode einer Konsolenanwendung einfügen, um ihn auszuführen. \(Denken Sie daran, unsicheren Code im **Projekt\-Designer** zu aktivieren. Wählen Sie in der Menüleiste **Projekt**, **Eigenschaften** aus, und wählen Sie dann **Unsicheren Code zulassen** auf der Registerkarte **Erstellen** aus.\)  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
  
```  
  
 Der Dereferenzierungsoperator kann nicht auf Zeiger vom Typ `void*` angewendet werden.  Sie können jedoch eine Umwandlung verwenden, um einen void\-Zeiger in einen anderen Zeigertyp und umgekehrt zu konvertieren.  
  
 Ein Zeiger kann den Wert `null` annehmen.  Die Anwendung des Dereferenzierungsoperators auf einen NULL\-Zeiger führt zu einem in der Implementierung definierten Verhalten.  
  
 Beachten Sie, dass die Übergabe von Zeigern zwischen Methoden zu nicht definiertem Verhalten führen kann.  Dies betrifft zum Beispiel die Rückgabe eines Zeigers an eine lokale Variable als Out\-Parameter, Ref\-Parameter oder als Funktionsergebnis.  Wenn der Zeiger in einem fixed\-Block festgelegt wurde, ist die Variable, auf die der Zeiger verweist, möglicherweise nicht fixiert.  
  
 In der folgenden Tabelle werden die Operatoren und Anweisungen aufgelistet, die in einem unsicheren Kontext auf Zeiger angewendet werden können.  
  
|Operator\/Anweisung|Verwendung|  
|-------------------------|----------------|  
|\*|Führt eine Zeigerdereferenzierung aus.|  
|\-\>|Greift über einen Zeiger auf einen Member einer Struktur zu.|  
|\[\]|Indiziert einen Zeiger.|  
|`&`|Ruft die Adresse einer Variablen ab.|  
|\+\+ und \-\-|Inkrementiert und dekrementiert Zeiger.|  
|\+ und \-|Führt Zeigerarithmetik aus.|  
|\=\=, \!\=, \<, \>, \<\= und \>\=|Vergleicht Zeiger.|  
|`stackalloc`|Belegt Speicher für den Stapel.|  
|`fixed`\-Anweisung|Fixiert eine Variable vorübergehend, damit ihre Adresse gefunden werden kann.|  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Zeigerkonvertierungen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)   
 [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)