---
title: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)
description: Die Split-Methode gibt ein Array mit Zeichenfolgen an, die von mehreren Trennzeichen getrennt werden. So können Sie auf einfache Weise Zeichenfolgen analysieren.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 7c5d8fa462775c6f3a9981693129997dda6c2286
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324141"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a>Analysieren von Zeichenfolgen mithilfe von String.Split in C\#

Die <xref:System.String.Split%2A?displayProperty=nameWithType>-Methode erstellt ein Array mit Teilzeichenfolgen, indem die Eingabezeichenfolge von mindestens einem Trennzeichen geteilt wird. Sie stellt in der Regel die einfachste Möglichkeit dar, eine Zeichenfolge an Wortgrenzen zu teilen. Sie wird außerdem verwendet, um Zeichenfolgen nach anderen bestimmten Zeichen und Zeichenfolgen zu trennen.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Mithilfe des folgenden Codes wird ein häufig verwendeter Ausdruck in ein Array mit Zeichenfolgen für jedes Wort unterteilt.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

Jede Instanz eines Trennzeichens gibt einen Wert in dem zurückgegebenen Array zurück. Aufeinander folgende Trennzeichen geben eine leere Zeichenfolge als Wert in einem zurückgegebenen Array zurück. Im folgenden Beispiel sehen Sie, wie ein leere Zeichenfolge erstellt wird. Hier wird das Leerzeichen als Trennzeichen verwendet.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

Dieses Verhalten vereinfacht den Vorgang für Formate wie CSV (Comma Separated Values, durch Trennzeichen getrennte Werte), die Tabellendaten darstellen. Aufeinander folgende Kommas stellen eine leere Spalte dar.

Sie können einen optionalen <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>-Parameter übergeben, um jegliche leeren Zeichenfolgen aus dem zurückgegebenen Array auszuschließen. Für kompliziertere Prozesse der zurückgegebenen Auflistung können Sie [LINQ](../programming-guide/concepts/linq/index.md) verwenden, um die Ergebnissequenz zu manipulieren.

<xref:System.String.Split%2A?displayProperty=nameWithType> kann mehrere Trennzeichen verwenden.
In diesem Beispiel werden Leerräume, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die an <xref:System.String.Split%2A> in einem Array übergeben werden.
Die Schleife am Ende des Codes zeigt sämtliche Wörter im zurückgegeben Array an.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

Aufeinander folgende Instanzen einer beliebigen Trennlinie geben die leere Zeichenfolge im Ausgabearray zurück:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<xref:System.String.Split%2A?displayProperty=nameWithType> kann ein Array mit Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../programming-guide/index.md)
- [Zeichenfolgen](../programming-guide/strings/index.md)
- [Reguläre Ausdrücke in .NET](../../standard/base-types/regular-expressions.md)
