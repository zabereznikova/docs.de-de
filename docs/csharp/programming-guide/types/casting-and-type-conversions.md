---
title: "Umwandlung und Typkonvertierungen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Typumwandlung [C#]"
  - "Konvertierungen [C#], Typ"
  - "Konvertieren von Typen [C#]"
  - "Datentypkonvertierung [C#]"
  - "Numerische Konvertierungen [C#]"
  - "Typkonvertierung [C#]"
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 52
---
# Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)
Da C\# zur Kompilierzeit statisch typisiert ist, kann eine Variable, nachdem sie deklariert wurde, nur dann erneut deklariert oder zum Speichern eines anderen Typs verwendet werden, wenn der betreffende Typ in den Typ der Variablen konvertiert werden kann.  Beispielsweise ist keine Konvertierung von einer ganzen Zahl in eine beliebigen Zeichenfolge möglich.  Wenn Sie `i` als ganze Zahl deklariert haben, können Sie dieser daher nicht die Zeichenfolge "Hello" zuweisen, wie im folgenden Code dargestellt.  
  
```c#  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 Eventuell ist es manchmal jedoch erforderlich, einen Wert in einen Variablenparameter oder einen Methodenparameter eines anderen Typs zu kopieren.  So verfügen Sie z. B. über eine ganzzahlige Variable, die Sie an eine Methode übergeben müssen, deren Parameter als `double` typisiert ist.  Oder Sie müssen einer Variablen eines Schnittstellentyps eine Klassenvariable zuweisen.  Solche Operationen werden als *Typkonvertierungen* bezeichnet.  In C\# können Sie die folgenden Arten von Konvertierungen ausführen:  
  
-   **Implizite Konvertierungen**: Es wird keine besondere Syntax benötigt, da die Konvertierung typsicher ist und keine Daten verloren gehen.  Die Beispiele umfassen Konvertierungen von kleineren in größere ganzzahlige Typen und Konvertierungen von abgeleiteten Klassen in Basisklassen.  
  
-   **Explizite Konvertierungen \(Umwandlungen\)**: Für explizite Konvertierungen ist ein Typumwandlungsoperator erforderlich.  Eine Umwandlung ist erforderlich, wenn Informationen bei der Konvertierung verloren gehen können oder wenn die Konvertierung aus anderen Gründen fehlschlägt. Typische Beispiele hierfür sind die numerische Konvertierung in einen Typ, der weniger Genauigkeit oder einen kleineren Bereich aufweist, und die Konvertierung einer Basisklasseninstanz in eine abgeleitete Klasse.  
  
-   **Benutzerdefinierte Konvertierungen**: Benutzerdefinierte Konvertierungen werden mit besonderen Methoden durchgeführt, die Sie definieren können, um explizite und implizite Konvertierungen zwischen benutzerdefinierten Typen durchzuführen, die keine von einer Basisklasse abgeleitete Klassenbeziehung aufweisen.  Weitere Informationen finden Sie unter [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Konvertierungen mit Hilfsklassen**: Um zwischen nicht kompatiblen Typen, z. B. ganzen Zahlen und <xref:System.DateTime?displayProperty=fullName>\-Objekten, oder Hexadezimalzeichenfolgen und Bytearrays, zu konvertieren, können Sie die <xref:System.BitConverter?displayProperty=fullName>\-Klasse verwenden, die <xref:System.Convert?displayProperty=fullName>\-Klasse und die `Parse`\-Methoden der integrierten numerischen Typen, wie z. B. <xref:System.Int32.Parse%2A?displayProperty=fullName>.  Weitere Informationen finden Sie unter [Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) und [Gewusst wie: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## Implizite Konvertierungen  
 Für integrierte numerische Typen kann eine implizite Konvertierung durchgeführt werden, wenn der zu speichernde Wert in die Variable passt, ohne abgeschnitten oder gerundet zu werden.  So kann z. B. eine Variable vom Typ [long](../../../csharp/language-reference/keywords/long.md) \(8\-Byte\-Ganzzahl\) jeden Wert speichern, der von einem [int](../../../csharp/language-reference/keywords/int.md) \(4 Byte auf einem 32\-Bit\-Computer\) gespeichert werden kann.  Im folgenden Beispiel konvertiert der Compiler implizit den Wert rechts in den Typ `long` und weist den Wert anschließend `bigNum` zu.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/casting-and-type-convers_1.cs)]  
  
 Eine vollständige Liste aller impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Für Referenztypen ist eine implizite Konvertierung immer aus einer Klasse in eine der direkten oder indirekten Basisklassen oder Schnittstellen vorhanden.  Es ist keine besondere Syntax erforderlich, da eine abgeleitete Klasse immer alle Member einer Basisklasse enthält.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## Explizite Konvertierungen  
 Wenn jedoch eine Konvertierung nicht ohne das Risiko eines Datenverlusts durchgeführt werden kann, ist für den Compiler eine explizite Konvertierung erforderlich, die als *Umwandlung* bezeichnet werden kann.  Eine Umwandlung ist eine Möglichkeit, den Compiler darüber zu informieren, dass Sie die Konvertierung durchführen möchten und dass Ihnen klar ist, dass ein Datenverlust auftreten kann.  Um eine Umwandlung durchzuführen, legen Sie den Typ, in den Sie umwandeln, in Klammern vor dem zu konvertierenden Wert oder der zu konvertierenden Variablen fest.  Im folgenden Programm wird [double](../../../csharp/language-reference/keywords/double.md) in [int](../../../csharp/language-reference/keywords/int.md) umgewandelt.  Ohne die Typumwandlung kann das Programm nicht kompiliert werden.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/casting-and-type-convers_2.cs)]  
  
 Eine Liste der expliziten numerischen Konvertierungen, die zulässig sind, finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
 Für Referenztypen ist eine explizite Umwandlung erforderlich, wenn Sie von einem Basistyp in einen abgeleiteten Typ umwandeln müssen:  
  
```c#  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Ein Umwandlungsvorgang zwischen Referenztypen führt nicht zu einer Änderung des Laufzeittyps des zugrunde liegenden Objekts, sondern lediglich zu einer Änderung des Typs für den Wert, der als Verweis auf dieses Objekt verwendet wird.  Weitere Informationen finden Sie unter [Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## Typkonvertierungsausnahmen zur Laufzeit  
 In einigen Referenztypkonvertierungen kann der Compiler nicht bestimmen, ob eine Umwandlung gültig ist.  Es ist möglich, dass eine Umwandlungsoperation, die ordnungsgemäß kompiliert, zur Laufzeit nicht ordnungsgemäß ausgeführt wird.  Wie im folgenden Beispiel dargestellt, führt eine Typumwandlung, die zur Laufzeit fehlschlägt, zm Auslösen einer <xref:System.InvalidCastException>.  
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/casting-and-type-convers_3.cs)]  
  
 C\# liefert die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md), damit Sie die Kompatibilität testen können, bevor Sie die Typumwandlung durchführen.  Weitere Informationen finden Sie unter [Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is"](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Enthaltenes Buchkapitel  
 [More About Variables](http://go.microsoft.com/fwlink/?LinkId=221230) in [Beginning Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [Operator \(\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [Explizit](../../../csharp/language-reference/keywords/explicit.md)   
 [Implizite](../../../csharp/language-reference/keywords/implicit.md)   
 [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Generalized Type Conversion](../Topic/Generalized%20Type%20Conversion.md)   
 [Exported Type Conversion](http://msdn.microsoft.com/de-de/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [Gewusst wie: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)