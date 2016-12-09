---
title: "Ändern der Groß-/Kleinschreibung"
description: "Ändern der Groß-/Kleinschreibung"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: f67c726b38657790deebb623dc44cb528fe404bc

---

# <a name="changing-case"></a>Ändern der Groß-/Kleinschreibung

Wenn Sie eine Anwendung schreiben, die Benutzereingaben akzeptiert, können Sie nicht sicher sein, ob die Daten in Groß- oder Kleinschreibung eingegeben werden. Häufig möchten Sie, dass Zeichenfolgen in einheitlicher Schreibung vorliegen, insbesondere, wenn sie in der Benutzeroberfläche angezeigt werden. In der folgenden Tabelle werden zwei Methoden zur Änderung der Groß-/Kleinschreibung beschrieben.

Methodenname | Verwendung
----------- | ---
[String.ToUpper](xref:System.String.ToUpper) | Konvertiert alle Zeichen in einer Zeichenfolge in Großbuchstaben.
[String.ToLower](xref:System.String.ToLower) | Konvertiert alle Zeichen in einer Zeichenfolge in Kleinbuchstaben.

> [!WARNING]  
> Beachten Sie, dass die `String.ToUpper`- und die `String.ToLower`-Methode nicht dazu verwendet werden sollten, Zeichenfolgen zu konvertieren, um diese zu vergleichen oder auf Gleichheit zu testen. 

## <a name="comparing-strings-of-mixed-case"></a>Vergleichen von Zeichenfolgen in gemischter Schreibung

Um Zeichenfolgen in gemischter Schreibung zu vergleichen, um zu bestimmen, ob sie gleich sind, rufen Sie eine der Überladungen der [String](xref:System)`Equals`-Methode mit einem *comparisonType*-Parameter auf, und geben Sie entweder den Wert von [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) für das *comparisonType*-Argument an. 

Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET Framework](best-practices.md). 

## <a name="toupper"></a>ToUpper

Die [String.ToUpper](xref:System.String.ToUpper)-Methode ändert alle Zeichen in einer Zeichenfolge in Großbuchstaben. Im folgenden Beispiel wird die Zeichenfolge „Hello World!“ von gemischter Schreibung in Großbuchstaben konvertiert.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a>ToLower

Die [String.ToLower](xref:System.String.ToLower)-Methode entspricht der vorherigen Methode mit dem Unterschied, dass sie alle Zeichen in einer Zeichenfolge in Kleinbuchstaben konvertiert. Im folgenden Beispiel wird die Zeichenfolge „Hello World!“ in Kleinbuchstaben konvertiert.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a>Siehe auch

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)



<!--HONumber=Nov16_HO3-->


