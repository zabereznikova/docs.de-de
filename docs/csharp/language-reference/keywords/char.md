---
title: char-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 63f8871926e8c279678c59a2256bef46b2ff514e
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698775"
---
# <a name="char-c-reference"></a>char (C#-Referenz)

Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=nameWithType>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet. Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).

 Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.

|type|Range|Size|.NET-Typ|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 in U+FFFF|Ein Unicode-Zeichen (16 Bit)|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Literale

Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden. Sie können auch die ganzzahligen Zeichencodes umwandeln. Im folgenden Beispiel werden die vier Elemente eines `char`-Arrays mit dem gleichen Zeichen `X` initialisiert:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Konvertierungen

Ein `char` kann implizit in ein [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) oder [decimal](../builtin-types/floating-point-numeric-types.md) konvertiert werden. Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.

Der Typ <xref:System.Char?displayProperty=nameWithType> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.

## <a name="c-language-specification"></a>C#-Sprachspezifikation  

Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- <xref:System.Char>
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Integrale Typen](../builtin-types/integral-numeric-types.md)
- [Tabelle integrierter Typen](./built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](./implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](./explicit-numeric-conversions-table.md)
- [Zeichenfolgen](../../programming-guide/strings/index.md)
