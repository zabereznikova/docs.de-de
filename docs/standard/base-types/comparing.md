---
title: Vergleichen von Zeichenfolgen
description: Vergleichen von Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 2ad585bd5475cf39aeae5dadc9ce3864c501a205

---

# <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen

.NET stellt mehrere Methoden bereit, um Werte von Zeichenfolgen zu vergleichen. In der folgenden Tabelle werden die Methoden zum Vergleichen von Werten aufgeführt und beschrieben.

Methodenname | Verwendung
----------- | ---
[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Vergleicht die Werte zweier Zeichenfolgen. Gibt einen Ganzzahlwert zurück.
[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Vergleicht zwei Zeichenfolgen, ohne die Einstellungen der lokalen Kultur zu berücksichtigen. Gibt einen Ganzzahlwert zurück.
[String.CompareTo](xref:System.String.CompareTo(System.String)) | Vergleicht das aktuelle Zeichenfolgenobjekt mit einer anderen Zeichenfolge. Gibt einen Ganzzahlwert zurück.
[String.StartsWith](xref:System.String.StartsWith(System.String)) | Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge beginnt. Gibt einen booleschen Wert zurück.
[String.EndsWith](xref:System.String.CompareTo(System.String)) | Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge endet. Gibt einen booleschen Wert zurück.
[String.Equals](xref:System.String.CompareTo(System.String)) | Stellt fest, ob zwei Zeichenfolgen identisch sind. Gibt einen booleschen Wert zurück.
[String.IndexOf](xref:System.String.IndexOf(System.Char)) | Gibt ausgehend vom Anfang der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück. Gibt einen Ganzzahlwert zurück.
[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) | Gibt ausgehend vom Ende der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück. Gibt einen Ganzzahlwert zurück.

## <a name="compare"></a>Vergleichen

Die statische [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode bietet umfassende Möglichkeiten zum Vergleichen von zwei Zeichenfolgen. Bei dieser Methode werden unterschiedliche Kulturen berücksichtigt. Sie können diese Funktion verwenden, um zwei Zeichenfolgen oder zwei untergeordnete Zeichenfolgen zweier Zeichenfolgen miteinander zu vergleichen. Zusätzlich sind Überladungen verfügbar, mit denen die Groß-/Kleinschreibung sowie abweichende Kulturen berücksichtigt bzw. ignoriert werden können. In der folgenden Tabelle sind die drei ganzzahligen Werte aufgeführt, die von dieser Methode zurückgegeben werden können. 

Rückgabewert | Bedingung
------------ | ---------
Eine negative ganze Zahl | Die erste Zeichenfolge steht in der Sortierreihenfolge vor der zweiten Zeichenfolge, oder die erste Zeichenfolge ist `null`.
0 | Die erste Zeichenfolge und die zweite Zeichenfolge sind gleich, oder beide Zeichenfolgen sind `null`.
Eine positive ganze Zahl oder 1. | Die erste Zeichenfolge folgt in der Sortierreihenfolge der zweiten Zeichenfolge, oder die zweite Zeichenfolge ist NULL.
 
> [!IMPORTANT]
> Die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.

Im folgenden Beispiel wird die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode verwendet, um das Verhältnis der Werte von zwei Zeichenfolgen festzustellen.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

In diesem Beispiel wird `-1` auf der Konsole angezeigt.

## <a name="compareordinal"></a>CompareOrdinal

Mithilfe der [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode werden zwei Zeichenfolgenobjekte verglichen, ohne dass die Einstellungen der lokalen Kultur berücksichtigt werden. Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen `Compare`-Methode zurückgegeben werden.

> [!IMPORTANT]
> Die [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.

Im folgenden Beispiel wird die `CompareOrdinal`-Methode verwendet, um die Werte von zwei Zeichenfolgen zu vergleichen.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

In diesem Beispiel wird `-32` auf der Konsole angezeigt.

## <a name="compareto"></a>CompareTo

Mit der [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode wird die im aktuellen Zeichenfolgenobjekt gekapselte Zeichenfolge mit einer anderen Zeichenfolge oder einem anderen Objekt verglichen. Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen `String.Compare`-Methode zurückgegeben werden.

> [!IMPORTANT]
> Die [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt. Sie sollten die [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist). Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.

Im folgenden Beispiel wird die `String.CompareTo`-Methode verwendet, um das `string1`-Objekt mit dem `string2`-Objekt zu vergleichen.

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

In diesem Beispiel wird `-1` auf der Konsole angezeigt.

## <a name="equals"></a>gleich

Mit der [String.Equals](xref:System.String.CompareTo(System.String))-Methode lässt sich auf einfache Weise feststellen, ob zwei Zeichenfolgen identisch sind. Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt den booleschen Wert `true` oder `false` zurück. Wie das nächste Beispiel zeigt, kann die Methode einer bestehenden Klasse verwendet werden. Im folgenden Beispiel wird mithilfe der `Equals`-Methode festgestellt, ob ein Zeichenfolgenobjekt den Ausdruck „Hello World“ enthält.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

In diesem Beispiel wird `true` auf der Konsole angezeigt.

Diese Methode kann auch als statische Methode verwendet werden. Im folgenden Beispiel werden zwei Zeichenfolgenobjekte mithilfe einer statischen Methode verglichen.

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

In diesem Beispiel wird `true` auf der Konsole angezeigt.

## <a name="startswith-and-endswith"></a>"StartsWith" und "EndsWith"

Mit der [String.StartsWith](xref:System.String.StartsWith(System.String))-Methode können Sie feststellen, ob ein Zeichenfolgenobjekt mit den gleichen Zeichen beginnt, die eine andere Zeichenfolge enthält. Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt `true` zurück, wenn das aktuelle Zeichenfolgenobjekt mit der übergebenen Zeichenfolge beginnt, und sie gibt `false` zurück, wenn dies nicht der Fall ist. Im folgenden Beispiel wird mithilfe dieser Methode festgestellt, ob ein Zeichenfolgenobjekt mit "Hello" beginnt.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

In diesem Beispiel wird `true` auf der Konsole angezeigt.

Bei der [String.EndsWith](xref:System.String.CompareTo(System.String))-Methode wird eine übergebene Zeichenfolge mit den Zeichen am Ende des aktuellen Zeichenfolgenobjekts verglichen. Auch sie gibt einen booleschen Wert zurück. Im folgenden Beispiel wird das Ende einer Zeichenfolge mithilfe der `EndsWith`-Methode überprüft.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

In diesem Beispiel wird `false` auf der Konsole angezeigt.

## <a name="indexof-and-lastindexof"></a>"IndexOf" und "LastIndexOf"

Mit der [String.IndexOf](xref:System.String.IndexOf(System.Char))-Methode können Sie die Position feststellen, an der ein bestimmtes Zeichen in einer Zeichenfolge erstmalig vorkommt. Bei dieser Methode, die die Groß-/Kleinschreibung beachtet, beginnt die Zählung am Anfang einer Zeichenfolge; sie gibt die Position eines übergebenen Zeichens auf der Grundlage eines nullbasierten Indizes zurück. Wenn das Zeichen nicht gefunden wird, wird der Wert –1 zurückgegeben.

Im folgenden Beispiel wird die `IndexOf`-Methode verwendet, um in einer Zeichenfolge nach dem ersten Vorkommnis des Zeichens '`l`' zu suchen.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

In diesem Beispiel wird `2` auf der Konsole angezeigt.

Die [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))-Methode ist vergleichbar mit der `String.IndexOf`-Methode, außer dass sie die Position zurückgibt, an der ein bestimmtes Zeichen innerhalb einer Zeichenfolge letztmalig vorkommt. Sie beachtet die Groß-/Kleinschreibung und verwendet einen nullbasierten Index. 

Im folgenden Beispiel wird die `LastIndexOf`-Methode verwendet, um in einer Zeichenfolge nach dem letzten Vorkommnis des Zeichens '`l`' zu suchen.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

In diesem Beispiel wird `9` auf der Konsole angezeigt.

Beide Methoden sind hilfreich, wenn sie in Verbindung mit der [String.Remove](xref:System.String.Remove(System.Int32))-Methode verwendet werden. Sie können die `IndexOf`-Methode oder die `LastIndexOf`-Methode verwenden, um die Position eines Zeichens abzurufen, und diese Position dann an die `Remove method` übergeben, um ein Zeichen oder ein Wort zu entfernen, das mit diesem Zeichen beginnt.

## <a name="see-also"></a>Siehe auch

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)















<!--HONumber=Nov16_HO3-->


