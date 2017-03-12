---
title: "Verwenden von Konstruktoren (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Konstruktoren [C#], Informationen über Konstruktoren"
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Verwenden von Konstruktoren (C#-Programmierhandbuch)
Wenn [\- Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) erstellt wird, wird der Konstruktor aufgerufen.  Konstruktoren haben den gleichen Namen wie die Klasse oder die Struktur, und sie initialisieren normalerweise die Datenmember des neuen Objekts.  
  
 Im folgenden Beispiel wird die Klasse `Taxi` durch einen einfachen Konstruktor definiert.  Anschließend wird diese Klasse mithilfe des Operators [new](../../../csharp/language-reference/keywords/new.md) instanziiert.  Der Operator `new` ruft den `Taxi`\-Konstruktor unmittelbar nach der Belegung von Arbeitsspeicher für das neue Objekt auf.  
  
 [!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_1.cs)]  
  
 Ein Konstruktor, der keine Parameter annimmt, wird als *Standardkonstruktor* bezeichnet.  Standardkonstruktoren werden immer dann aufgerufen, wenn ein Objekt mit dem Operator `new` instanziiert wird und keine Argumente für `new` bereitgestellt werden.  Weitere Informationen finden Sie unter [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Alle nicht [statischen](../../../csharp/language-reference/keywords/static.md) Klassen ohne Konstruktoren erhalten vom C\#\-Compiler einen öffentlichen Standardkonstruktor, um die Klasseninstanziierung zu ermöglichen.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Sie können verhindern, dass eine Klasse instanziiert wird, indem Sie den Konstruktor auf folgende Art und Weise privat machen:  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_2.cs)]  
  
 Weitere Informationen finden Sie unter [Private Konstruktoren](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 Konstruktoren für [struct](../../../csharp/language-reference/keywords/struct.md)\-Typen ähneln Klassenkonstruktoren. Allerdings können `structs` keinen expliziten Standardkonstruktor enthalten, da dieser automatisch vom Compiler bereitgestellt wird.  Dieser Konstruktor initialisiert alle Felder in `struct` mit den Standardwerten.  Weitere Informationen finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  Allerdings wird dieser Standardkonstruktor nur aufgerufen, wenn `struct` mit `new` instanziiert wird.  Im folgenden Code wird beispielsweise der Standardkonstruktor für <xref:System.Int32> verwendet, sodass sichergestellt ist, dass der ganzzahlige Typ initialisiert wird:  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Der folgende Code verursacht allerdings einen Compilerfehler, da `new` nicht verwendet und versucht wird, ein Objekt zu verwenden, das nicht initialisiert wurde:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 Alternativ können auf `structs` basierende Objekte, einschließlich aller integrierten numerischen Typen, initialisiert oder zugewiesen und anschließend wie im folgenden Beispiel verwendet werden:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Das Aufrufen des Standardkonstruktors für einen Werttyp ist demnach nicht erforderlich.  
  
 Sowohl in Klassen als auch in `structs` können Konstruktoren definiert werden, die Parameter entgegennehmen.  Konstruktoren, die Parameter annehmen, müssen durch eine `new`\-Anweisung oder eine [Basisanweisung](../../../csharp/language-reference/keywords/base.md) aufgerufen werden.  In Klassen und `structs` können auch mehrere Konstruktoren definiert werden, und es ist in beiden Fällen nicht erforderlich, einen Standardkonstruktor zu definieren.  Beispiel:  
  
 [!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_3.cs)]  
  
 Diese Klasse kann mit einer der beiden folgenden Anweisungen erstellt werden:  
  
 [!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_4.cs)]  
  
 Mithilfe des `base`\-Schlüsselworts kann ein Konstruktor den Konstruktor einer Basisklasse aufrufen.  Beispiel:  
  
 [!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_5.cs)]  
  
 In diesem Beispiel wird der Konstruktor der Basisklasse aufgerufen, bevor der Konstruktorblock ausgeführt wird.  Das `base`\-Schlüsselwort kann mit oder ohne Parameter verwendet werden.  Alle Parameter, die dem Konstruktor übergeben wurden, können als Parameter für `base` oder als Teil eines Ausdrucks verwendet werden.  Weitere Informationen finden Sie unter [Basis](../../../csharp/language-reference/keywords/base.md).  
  
 Wenn ein Basisklassenkonstruktor in einer abgeleiteten Klasse nicht explizit mit dem `base`\-Schlüsselwort aufgerufen wird, wird implizit der Standardkonstruktor \(sofern vorhanden\) aufgerufen.  Dies bedeutet, dass die folgenden Konstruktordeklarationen dieselben Auswirkungen haben:  
  
 [!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_6.cs)]  
  
 [!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_7.cs)]  
  
 Wenn eine Basisklasse keinen Standardkonstruktor bereitstellt, muss die abgeleitete Klasse den Basiskonstruktor mithilfe von `base` explizit aufrufen.  
  
 Ein Konstruktor kann einen anderen Konstruktor in demselben Objekt aufrufen, indem er das [this](../../../csharp/language-reference/keywords/this.md)\-Schlüsselwort verwendet.  Wie `base` kann auch `this` mit oder ohne Parameter verwendet werden, und alle dem Konstruktor übergebenen Parameter können als Parameter für `this` oder als Teil eines Ausdrucks verwendet werden.  So kann zum Beispiel der zweite Konstruktor im vorigen Beispiel mit `this` umgeschrieben werden:  
  
 [!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_8.cs)]  
  
 Die Verwendung des `this`\-Schlüsselworts im vorherigen Beispiel bewirkt das Aufrufen dieses Konstruktors:  
  
 [!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-constructors_9.cs)]  
  
 Konstanten können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected` `internal` gekennzeichnet werden.  Diese Zugriffsmodifizierer definieren, auf welche Weise Benutzer der Klasse die Klasse konstruieren können.  Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Ein Konstruktor kann mithilfe des [static](../../../csharp/language-reference/keywords/static.md)\-Schlüsselworts als statisch deklariert werden.  Statische Konstruktoren werden unmittelbar vor dem Zugriff auf statische Felder automatisch aufgerufen. Im Allgemeinen werden mit ihrer Hilfe statische Klassenmember initialisiert.  Weitere Informationen finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)