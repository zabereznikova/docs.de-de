---
title: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen
description: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 6105861882c3bfd525a2d902fd2600f5da10417d

---

# <a name="trimming-and-removing-characters-from-strings"></a>Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen

Wenn Sie einen Satz in einzelne Wörter auflösen, erhalten Sie möglicherweise Wörter mit Leerzeichen (auch als Leerräume bezeichnet) auf beiden Seiten des jeweiligen Wortes. In diesem Fall können Sie eine der Entfernungsmethoden aus der [System.String](https://docs.microsoft.com/dotnet/core/api/System.String)-Klasse verwenden, um an einer bestimmten Position der Zeichenfolge eine beliebige Anzahl von Leerzeichen oder anderen Zeichen zu entfernen. In der folgenden Tabelle sind die verfügbaren Entfernungsmethoden aufgeführt.

Methodenname | Verwendung
----------- | ---
[String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | Entfernt in einem Zeichenarray angegebene Leerzeichen am Anfang und Ende einer Zeichenfolge.
[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) | Entfernt in einem Zeichenarray angegebene Zeichen am Ende einer Zeichenfolge.
[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) | Entfernt in einem Zeichenarray angegebene Zeichen am Anfang einer Zeichenfolge.
[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) | Entfernt eine festgelegte Anzahl von Zeichen an der angegebenen Indexposition in einer Zeichenfolge.


## <a name="trim"></a>Trim

Wie das folgende Beispiel zeigt, lassen sich mit der [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim)-Methode Leerzeichen an beiden Enden einer Zeichenfolge auf einfache Weise entfernen.

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

Sie können auch Zeichen am Anfang und am Ende einer Zeichenfolge entfernen, die Sie in einem Zeichenarray angeben. Im folgenden Beispiel werden Leerzeichen, Punkte und Sternchen entfernt.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a>TrimEnd

Mit der [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))-Methode werden Zeichen am Ende einer Zeichenfolge entfernt, wodurch ein neues Zeichenfolgenobjekt entsteht. An diese Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält. Die Reihenfolge der Elemente im Zeichenarray hat keine Auswirkungen auf den Entfernungsvorgang. Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.

Im folgenden Beispiel werden die letzten Buchstaben einer Zeichenfolge mit der TrimEnd-Methode entfernt. In diesem Beispiel werden die Positionen der Zeichen `'r'` und `'W'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt. Beachten Sie, dass durch diesen Code das letzte Wort von `MyString` sowie ein Teil des ersten Wortes entfernt wird.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Durch diesen Code wird `He` auf der Konsole angezeigt.

Im folgenden Beispiel wird das letzte Wort einer Zeichenfolge mit der [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))-Methode entfernt. Im Code folgt auf das Wort `Hello` ein Komma. Da das Komma im Zeichenarray nicht als zu entfernendes Zeichen angegeben ist, wird der Vorgang beim Komma beendet.

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Durch diesen Code wird `Hello,` auf der Konsole angezeigt.

## <a name="trimstart"></a>TrimStart

Die [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))-Methode ist mit der [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))-Methode vergleichbar, außer dass eine neue Zeichenfolge erstellt wird, indem Zeichen am Anfang eines bestehenden Zeichenfolgenobjekts entfernt werden. An die [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))-Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält. Wie bei der [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))-Methode hat die Reihenfolge der Elemente im Zeichenarray keine Auswirkungen auf den Entfernungsvorgang. Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.

Im folgenden Beispiel wird das erste Wort einer Zeichenfolge entfernt. In diesem Beispiel werden die Positionen der Zeichen `'l'` und `'H'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

Durch diesen Code wird `World!` auf der Konsole angezeigt.

## <a name="remove"></a>Remove

Mit der [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))-Methode wird an einer festgelegten Position innerhalb einer bestehenden Zeichenfolge eine festgelegte Anzahl von Zeichen entfernt. Diese Methode setzt einen nullbasierten Index voraus.

Im folgenden Beispiel werden ausgehend von der fünften Position des nullbasierten Zeichenfolgenindizes zehn Zeichen aus einer Zeichenfolge entfernt.

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

Sie können auch ein bestimmtes Zeichen oder eine Teilzeichenfolge aus einer Zeichenfolge entfernen, indem Sie die [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String))-Methode aufrufen und eine leere Zeichenfolge ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) zum Ersetzen angeben. Im folgenden Beispiel werden alle Kommas in einer Zeichenfolge entfernt.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a>Siehe auch

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)




<!--HONumber=Nov16_HO3-->


