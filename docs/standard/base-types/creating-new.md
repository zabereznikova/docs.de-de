---
title: Erstellen neuer Zeichenfolgen
description: Erstellen neuer Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 29a0ca2d58bb6ae037a97c84a53ce388da2dbeae

---

# <a name="creating-new-strings"></a>Erstellen neuer Zeichenfolgen

.NET ermöglicht das Erstellen von Zeichenfolgen mithilfe einer einfachen Zuweisung und überlädt auch einen Klassenkonstruktor, um die Zeichenfolgenerstellung mithilfe einer Reihe verschiedener Parameter zu unterstützen. .NET stellt auch verschiedene Methoden in der [System.String](xref:System.String)-Klasse bereit, die durch Kombinieren verschiedener Zeichenfolgen, Zeichenfolgenarrays oder Objekte neue Zeichenfolgenobjekte erstellen. 

## <a name="creating-strings-using-assignment"></a>Erstellen von Zeichenfolgen mithilfe von Zuweisung

Die einfachste Möglichkeit, ein neues [String](xref:System.String)-Objekt zu erstellen, ist die Zuweisung eines Zeichenfolgenliterals zu einem [String](xref:System.String)-Objekt. 

## <a name="creating-strings-using-a-class-constructor"></a>Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors

Sie können Überladungen des [String](xref:System.String)-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen. Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren. 

## <a name="methods-that-return-strings"></a>Methoden, die Zeichenfolgen zurückgeben

Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.

Methodenname | Verwendung
----------- | ---
[String.Format](xref:System.String.Format(System.String,System.Object)) | Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.
[String.Concat](xref:System.String.Concat(System.String,System.String)) | Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.
[String.Join](xref:System.String.Join(System.String,System.String[])) |Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.
[String.Insert](xref:System.String.Insert(System.Int32,System.String)) | Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.
[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32)) | Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.

### <a name="format"></a>Format

Sie können die `String.Format`-Methode verwenden, um formatierte Zeichenfolgen zu erstellen und Zeichenfolgen zu verketten, die mehrere Objekte darstellen. Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge. Wenn Ihre Anwendung z.B. dem Benutzer einen [Int32](xref:System.Int32)-Wert und einen [DateTime](xref:System.DateTime)-Wert anzeigen soll, können Sie ganz einfach mithilfe der `Format`-Methode eine Zeichenfolge erstellen, um diese Werte darzustellen. Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](composite-format.md).

Das folgende Beispiel verwendet die `Format`-Methode, um eine Zeichenfolge zu erstellen, die eine ganzzahlige Variable verwendet.

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

In diesem Beispiel zeigt [DateTime.Now](xref:System.DateTime.Now) das aktuelle Datum und die aktuelle Uhrzeit so an, wie es von der mit dem aktuellen Thread verknüpften Kultur angegeben ist.

### <a name="concat"></a>Concat

Die `String.Concat`-Methode kann verwendet werden, um ganz einfach aus mindestens zwei vorhandenen Objekten ein neues Zeichenfolgenobjekt zu erstellen. Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen. Diese Methode akzeptiert alle von `System.Object` abgeleiteten Klassen. Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a>Join

Die `String.Join`-Methode erstellt eine neue Zeichenfolge aus einem Array aus Zeichenfolgen und einem Trennzeichen. Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.

Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a>Insert

Die `String.Insert`-Methode erstellt eine neue Zeichenfolge, indem sie eine Zeichenfolge an einer angegebenen Position in einer anderen Zeichenfolge einfügt. Diese Methode verwendet einen nullbasierten Index. Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a>CopyTo

Die `String.CopyTo`-Methode kopiert Teile einer Zeichenfolge in ein Zeichenarray. Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben. Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen. Alle Indizes sind nullbasiert.

Das folgende Beispiel verwendet die `CopyTo`-Methode, um die Zeichen des Worts „Hello“ aus einem Zeichenfolgenobjekt in die erste Indexposition eines Zeichenarrays zu kopieren.

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a>Siehe auch

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)

[Kombinierte Formatierung](composite-format.md)




<!--HONumber=Nov16_HO3-->


