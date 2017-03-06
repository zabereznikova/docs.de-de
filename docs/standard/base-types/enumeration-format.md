---
title: Enumerationsformatzeichenfolgen
description: Enumerationsformatzeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 4d581898-99bc-42c3-816c-d8238f45096f
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 804884f75eb30764c0b8aaf2c8cd115029811157
ms.lasthandoff: 03/02/2017

---

# <a name="enumeration-format-strings"></a>Enumerationsformatzeichenfolgen

Sie können die [Enum.ToString](xref:System.Enum.ToString)-Methode verwenden, um ein neues Zeichenfolgenobjekt zu erstellen, das den numerischen, den hexadezimalen oder den Zeichenfolgenwert eines Enumerationsmembers darstellt. Diese Methode akzeptiert eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, der zurückgegeben werden soll.

In den folgenden Abschnitten werden die Enumerationsformatzeichenfolgen sowie die Werte aufgeführt, die diese zurückgeben. Bei diesen Formatbezeichnern wird die Groß- und Kleinschreibung nicht berücksichtigt.

## <a name="the-g-or-g-format-strings"></a>Die Formatzeichenfolgen „G“ bzw. „g“

Die Formatzeichenfolgen „G“ bzw. „g“ zeigen den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an, andernfalls zeigen sie den ganzzahligen Wert der aktuellen Instanz an. Wenn die Enumeration mit festgelegtem `Flags`-Attribut definiert ist, werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn das `Flags`-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt. Das folgende Beispiel veranschaulicht den Formatbezeichner „G“.

```csharp
Console.WriteLine(ConsoleColor.Red.ToString("G"));         // Displays Red
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("G"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Red.ToString("G"))           ' Displays Red
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("G"))     ' Displays Hidden, Archive
```

## <a name="the-f-or-f-format-strings"></a>Die Formatzeichenfolgen „F“ bzw. „f“

Die Formatzeichenfolgen „F“ bzw. „f“ zeigen den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an. Wenn der Wert vollständig als Summe der Einträge in der Enumeration angezeigt werden kann (selbst wenn das `Flags`-Attribut nicht vorhanden ist), werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn der Wert nicht vollständig durch die Enumerationseinträge ermittelt werden kann, wird der Wert als ganzzahliger Wert formatiert. Das folgende Beispiel veranschaulicht den Formatbezeichner „F“.

```csharp
Console.WriteLine(ConsoleColor.Blue.ToString("F"));       // Displays Blue
FileAttributes attributes = FileAttributes.Hidden | 
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("F"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Blue.ToString("F"))         ' Displays Blue
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("F"))     ' Displays Hidden, Archive
```

## <a name="the-d-or-d-format-strings"></a>Die Formatzeichenfolgen „D“ bzw. „d“

Die Formatzeichenfolgen „D“ bzw. „d“ zeigen den Enumerationseintrag in der kürzestmöglichen Darstellung als ganzzahligen Wert an. Das folgende Beispiel veranschaulicht den Formatbezeichner „D“.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("D"));         // Displays 11
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("D"));                // Displays 34
````

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("D"))           ' Displays 11
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("D"))                  ' Displays 34 
```

## <a name="the-x-or-x-format-strings"></a>Die Formatzeichenfolgen „X“ bzw. „x“

Die Formatzeichenfolgen „X“ bzw. „x“ zeigen den Enumerationseintrag als Hexadezimalwert an. Der Wert wird mit so vielen führenden Nullen wie nötig dargestellt, um sicherzustellen, dass der Wert mindestens acht Stellen lang ist. Das folgende Beispiel veranschaulicht den Formatbezeichner „X“.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("X"));   // Displays 0000000B
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("X"));          // Displays 00000022
```

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("X"))     ' Displays 0000000B
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("X"))            ' Displays 00000022 
```

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine Enumeration namens `Colors`, die aus drei Einträgen besteht: `Red`, `Blue` und `Green`.

 ```csharp
 public enum Color {Red = 1, Blue = 2, Green = 3}
```

```vb
Public Enum Color
   Red = 1
   Blue = 2
   Green = 3
End Enum
```

Nachdem die Enumeration definiert wurde, kann auf folgende Weise eine Instanz deklariert werden.

```csharp
Color myColor = Color.Green;
```

```vb
Dim myColor As Color = Color.Green
```

Dann kann die `Color.ToString(System.String)`-Methode verwendet werden, um den Enumerationswert je nach übergebenem Formatbezeichner auf verschiedene Arten anzuzeigen.

```csharp
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("G"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("F"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("D"));
Console.WriteLine("The value of myColor is 0x{0}.", 
                  myColor.ToString("X"));
// The example displays the following output to the console:
//       The value of myColor is Green.
//       The value of myColor is Green.
//       The value of myColor is 3.
//       The value of myColor is 0x00000003.
```

```vb
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("G"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("F"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("D"))
Console.WriteLine("The value of myColor is 0x{0}.", _
                  myColor.ToString("X"))
' The example displays the following output to the console:
'       The value of myColor is Green.
'       The value of myColor is Green.
'       The value of myColor is 3.
'       The value of myColor is 0x00000003. 
```

## <a name="see-also"></a>Siehe auch

[Formatierung von Typen](formatting-types.md)


