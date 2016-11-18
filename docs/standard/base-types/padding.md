---
title: "Auffüllen von Zeichenfolgen"
description: "Auffüllen von Zeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: b6c5d4c8a35aebdfca88801118cdeba25c0a7e65

---

# <a name="padding-strings"></a>Auffüllen von Zeichenfolgen

Verwenden Sie eine der folgenden [System.String](xref:System.String)-Methoden, um eine neue Zeichenfolge zu erstellen, die aus einer ursprünglichen Zeichenfolge besteht, die mit voran- oder nachgestellten Zeichen auf eine angegebene Gesamtlänge aufgefüllt wird. Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden, sodass die Zeichenfolge entweder rechtsbündig oder linksbündig ausgerichtet angezeigt wird.

Methodenname | Verwendung
----------- | ---
[String.PadLeft](xref:System.String.PadLeft(System.Int32)) | Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.
[String.PadRight](xref:System.String.PadRight(System.Int32)) | Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.

## <a name="padleft"></a>PadLeft

Die [String.PadLeft](xref:System.String.PadLeft(System.Int32))-Methode erstellt eine neue Zeichenfolge durch die Verkettung einer ausreichenden Anzahl vorangestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen. Die [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32))-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) können Sie Ihre eigenen Auffüllzeichen angeben.

Im folgenden Codebeispiel wird über die Methode [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist. In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a>PadRight

Die [String.PadRight](xref:System.String.PadRight(System.Int32))-Methode erstellt eine neue Zeichenfolge durch die Verkettung einer ausreichenden Anzahl nachgestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen. Die [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32))-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) können Sie Ihre eigenen Auffüllzeichen angeben.

Im folgenden Codebeispiel wird über die Methode [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist. In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a>Siehe auch

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)




<!--HONumber=Nov16_HO3-->


