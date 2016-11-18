---
title: Analysieren anderer Zeichenfolgen in .NET
description: Analysieren anderer Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: bf3fc05428ed491e7658951f002a9af17dcba5df

---

# <a name="parsing-other-strings-in-net"></a>Analysieren anderer Zeichenfolgen in .NET

Neben den numerischen und den [DateTime](xref:System.DateTime)-Zeichenfolgen können Sie auch Zeichenfolgen, die die Typen [Char](xref:System.Char), [Boolean](xref:System.Boolean) und [Enum](xref:System.Enum) darstellen, in Datentypen analysieren.

## <a name="char"></a>Char

Die statische Parse-Methode, die dem [Char](xref:System.Char)-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert. Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a>Boolesch

Der [Boolean](xref:System.Boolean)-Datentyp enthält eine [Parse](xref:System.Boolean.Parse(System.String))-Methode, mit der Sie eine Zeichenfolge, die einen `Boolean`-Wert darstellt, in einen tatsächlichen `Boolean`-Typ konvertieren können. Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren. Die dem `Boolean`-Typ zugeordnete `Parse`-Methode kann auch Zeichenfolgen analysieren, die von Leerzeichen eingeschlossen sind. Wenn eine beliebige andere Zeichenfolge übergeben wird, wird eine [FormatException](xref:System.FormatException) ausgelöst.

Im folgenden Codebeispiel wird die `Parse`-Methode zum Konvertieren einer Zeichenfolge in einen `Boolean`-Wert verwendet.

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a>Enumeration

Mit der statischen [Parse](xref:System.Enum.Parse(System.Type,System.String))-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren. Diese Methode akzeptiert den zu analysierenden Enumerationstyp, die zu analysierende Zeichenfolge und ein optionales `Boolean`-Flag, das angibt, ob bei der Analyse die Groß-/Kleinschreibung beachtet wird. Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können. Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.

Im folgenden Beispiel wird die `Parse`-Methode zum Konvertieren einer Zeichenfolgendarstellung in einen Enumerationswert verwendet. Die [DayOfWeek](xref:System.DayOfWeek)-Enumeration wird über eine Zeichenfolge mit Donnerstag initialisiert.

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a>Siehe auch

[Analysieren von Zeichenfolgen in .NET](parsing-strings.md)

[Formatieren von Typen in .NET](formatting-types.md)

[Typkonvertierung in .NET](type-conversion.md)




<!--HONumber=Nov16_HO3-->


