---
title: string (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: 66b1729363878f69f868b8b8fd6e9e7011426f27
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672003"
---
# <a name="string-c-reference"></a>string (C#-Referenz)

Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar. `string` ist ein Alias für <xref:System.String> in .NET.

Obwohl `string` ein Verweistyp ist, werden die Gleichheitsoperatoren (`==` und `!=`) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert. Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver. Zum Beispiel:

```csharp
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine((object)a == (object)b);
```

Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.

Der Operator „+“ verkettet Zeichenfolgen:

```csharp
string a = "good " + "morning";
```

Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.

Zeichenfolgen sind *unveränderlich*. Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre. Wenn Sie z.B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird b zugewiesen. Die Zeichenfolge „h“ ist anschließend für die automatische Speicherbereinigung auswählbar.

```csharp
string b = "h";
b += "ello";
```

Der []-Operator kann für schreibgeschützten Zugriff auf einzelne Zeichen eines `string` verwendet werden:

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und @-quoted. Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:

```csharp
"good morning"  // a string literal
```

Zeichenfolgenliterale können jeden Zeichenliteral enthalten. Escapesequenzen sind enthalten. Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.

```csharp
string a = "\\\u0066\n";
Console.WriteLine(a);
```

> [!NOTE]
> Der Escapecode `\udddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar. Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.

Wörtliche Zeichenfolgenliterale beginnen mit `@` und sind ebenfalls in doppelte Anführungszeichen eingeschlossen. Zum Beispiel:

```csharp
@"good morning"  // a string literal
```

Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z.B. das Schreiben eines vollqualifizierten Dateinamens erleichtert wird:

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

Informationen zu anderen Verwendungsmöglichkeiten des Sonderzeichens `@` finden Sie unter [@ -- verbatim identifier (@ (wörtlicher Bezeichner))](../tokens/verbatim.md).

Weitere Informationen zu Zeichenfolgen in C# finden Sie unter [Zeichenfolgen](../../programming-guide/strings/index.md).

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#17)]  

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../standard/base-types/best-practices-strings.md)
- [C#-Schlüsselwörter](index.md)
- [Verweistypen](reference-types.md)
- [Werttypen](value-types.md)
- [Grundlegende Zeichenfolgenoperationen](../../../standard/base-types/basic-string-operations.md)
- [Erstellen neuer Zeichenfolgen](../../../standard/base-types/creating-new.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md)
