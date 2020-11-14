---
title: Aufteilen von Zeichenfolgen in Teilzeichenfolgen
description: Lernen Sie verschiedene Techniken zum Extrahieren von Teilzeichenfolgen kennen, darunter String.Split, reguläre Ausdrücke und String.Substring.
ms.date: 10/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: 88947c4576b0496e4b4e45042d665e3ca5857c53
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403475"
---
# <a name="extract-substrings-from-a-string"></a>Extrahieren von Teilzeichenfolgen aus einer Zeichenfolge

In diesem Artikel werden verschiedene Techniken zum Extrahieren von Teilen einer Zeichenfolge behandelt.

- Verwenden Sie die [Split-Methode](#stringsplit-method), wenn die gewünschten Teilzeichenfolgen durch ein bekanntes Trennzeichen (oder mehrere) getrennt sind.
- [Reguläre Ausdrücke](#regular-expressions) sind nützlich, wenn die Zeichenfolge einem festen Muster entspricht.
- Verwenden Sie die Methoden [IndexOf und Substring](#stringindexof-and-stringsubstring-methods) in Verbindung miteinander, wenn Sie nicht *alle* Teilzeichenfolgen in einer Zeichenfolge extrahieren möchten.

## <a name="stringsplit-method"></a>String.Split-Methode

<xref:System.String.Split%2A?displayProperty=nameWithType> bietet mehrere Überladungen, die Ihnen helfen, eine Zeichenfolge in eine Gruppe von Teilzeichenfolgen zu zerlegen, die auf einem oder mehreren von Ihnen angegebenen Trennzeichen basieren. Sie können die Gesamtanzahl der Teilzeichenfolgen im Endergebnis begrenzen, Leerzeichen aus Teilzeichenfolgen entfernen oder leere Teilzeichenfolgen ausschließen.

Die folgenden Beispiele zeigen drei verschiedene Überladungen von `String.Split()`. Im ersten Beispiel wird die Überladung <xref:System.String.Split(System.Char[])> ohne Übergabe von Trennzeichen aufgerufen. Wenn Sie keine Trennzeichen angeben, verwendet `String.Split()` Standardtrennzeichen, bei denen es sich um Leerzeichen handelt, um die Zeichenfolge aufzuteilen.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

Wie Sie sehen können, sind die Punktzeichen (`.`) in zwei der Teilzeichenfolgen enthalten. Wenn Sie die Punktzeichen ausschließen möchten, können Sie das Punktzeichen als zusätzliches Trennzeichen hinzufügen. Im nächsten Beispiel wird gezeigt, wie dies geschieht.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

Die Punkte sind aus den Teilzeichenfolgen verschwunden, aber jetzt wurden zwei zusätzliche leere Teilzeichenfolgen eingefügt. Diese leere Teilzeichenfolge stellt die Teilzeichenfolge zwischen dem Wort und dem darauf folgenden Punkt dar. Um leere Teilzeichenfolgen aus dem resultierenden Array auszuschließen, können Sie die Überladung <xref:System.String.Split(System.Char[],System.StringSplitOptions)> aufrufen und <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> für den Parameter `options` angeben.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a>Reguläre Ausdrücke

Wenn Ihre Zeichenfolge mit einem festen Muster übereinstimmt, können Sie mit einem regulären Ausdruck dessen Elemente extrahieren und verarbeiten. Wenn Zeichenfolgen zum Beispiel die Form „ *Zahl* *Operand* *Zahl* “ haben, können Sie einen [regulären Ausdruck](regular-expressions.md) verwenden, um die Zeichenfolge zu extrahieren und die Elemente der Zeichenfolge zu verarbeiten. Hier sehen Sie ein Beispiel:

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

Das Muster für reguläre Ausdrücke, `(\d+)\s+([-+*/])\s+(\d+)`, ist so definiert:

|Muster|Beschreibung|
|-------------|-----------------|
|`(\d+)`|Übereinstimmung mit mindestens einer Dezimalstelle finden. Dies ist die erste Erfassungsgruppe.|
|`\s+`|Übereinstimmung mit mindestens einem Leerzeichen finden.|
|`([-+*/])`|Übereinstimmung mit dem Zeichen eines arithmetischen Operators (+, -, * oder /) finden. Dies ist die zweite Erfassungsgruppe.|
|`\s+`|Übereinstimmung mit mindestens einem Leerzeichen finden.|
|`(\d+)`|Übereinstimmung mit mindestens einer Dezimalstelle finden. Dies ist die dritte Erfassungsgruppe.|

Sie können auch einen regulären Ausdruck verwenden, um Teilzeichenfolgen aus einer Zeichenfolge zu extrahieren, die auf einem Muster statt auf einem festen Satz von Zeichen basieren. Dies ist ein gängiges Szenario, wenn eine der folgenden Bedingungen zutrifft:

- Mindestens eines der Trennzeichen dient in der <xref:System.String>-Instanz nicht *immer* als Trennzeichen.

- Sequenz und Anzahl der Trennzeichen sind variabel oder unbekannt.

Beispielsweise kann die <xref:System.String.Split%2A>-Methode nicht verwendet werden, um die folgende Zeichenfolge aufzuteilen, da die Anzahl von `\n`-Zeichen (Zeilenvorschub) variabel ist und sie nicht immer als Trennzeichen dienen.

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

Ein regulärer Ausdruck kann diese Zeichenfolge problemlos aufteilen, wie im folgenden Beispiel gezeigt.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

Das Muster für reguläre Ausdrücke, `\[([^\[\]]+)\]`, ist so definiert:

|Muster|Beschreibung|
|-------------|-----------------|
|`\[`|Übereinstimmung mit einer öffnenden geschweiften Klammer finden.|
|`([^\[\]]+)`|Einmal oder mehrmals eine Übereinstimmung mit einem beliebigen Zeichen finden, das keine öffnende oder schließende eckige Klammer ist. Dies ist die erste Erfassungsgruppe.|
|`\]`|Übereinstimmung mit einer schließenden geschweiften Klammer finden.|

Die Methode <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> ist fast identisch mit <xref:System.String.Split%2A?displayProperty=nameWithType>, außer dass sie eine Zeichenfolge auf Grundlage eines Musters regulärer Ausdrücke anstelle eines festen Satzes von Zeichen aufteilt. Im folgenden Beispiel wird beispielsweise die <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>-Methode verwendet, um eine Zeichenfolge mit Teilzeichenfolgen zu teilen, die durch verschiedene Kombinationen von Bindestrichen und anderen Zeichen voneinander getrennt sind.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

Das Muster für reguläre Ausdrücke, `\s-\s?[+*]?\s?-\s`, ist so definiert:

|Muster|Beschreibung|
|-------------|-----------------|
|`\s-`|Übereinstimmung mit einem Leerzeichen gefolgt von einem Bindestrich finden.|
|`\s?`|Übereinstimmung mit keinem oder einem Leerzeichen finden.|
|`[+*]?`|Übereinstimmung mit null oder einem Vorkommen von entweder dem Zeichen + oder * finden.|
|`\s?`|Übereinstimmung mit keinem oder einem Leerzeichen finden.|
|`-\s`|Übereinstimmung mit einem Bindestrich gefolgt von einem Leerzeichen finden.|

## <a name="stringindexof-and-stringsubstring-methods"></a>Die Methoden String.IndexOf und String.Substring

Wenn Sie nicht an allen Teilzeichenfolgen in einer Zeichenfolge interessiert sind, können Sie auch mit einer der Methoden zum Vergleichen von Zeichenfolgen arbeiten, die den Index zurückgibt, bei dem die Übereinstimmung beginnt. Sie können dann die <xref:System.String.Substring%2A>-Methode aufrufen, um die gewünschte Teilzeichenfolge zu extrahieren. Es gibt die folgenden Methoden zum Vergleichen von Zeichenfolgen:

- <xref:System.String.IndexOf%2A>, die den auf null basierenden Index des ersten Vorkommens eines Zeichens oder einer Zeichenfolge in einer Zeichenfolgeninstanz zurückgibt.

- <xref:System.String.IndexOfAny%2A>, die den auf null basierenden Index in der aktuellen Zeichenfolgeninstanz beim ersten Vorkommen eines beliebigen Zeichens in einem Zeichenarray zurückgibt.

- <xref:System.String.LastIndexOf%2A>, die den auf null basierenden Index des letzten Vorkommens eines Zeichens oder einer Zeichenfolge in einer Zeichenfolgeninstanz zurückgibt.

- <xref:System.String.LastIndexOfAny%2A>, die einen auf null basierenden Index in der aktuellen Zeichenfolgeninstanz des letzten Vorkommens eines beliebigen Zeichens in einem Zeichenarray zurückgibt.

Im folgenden Beispiel wird die <xref:System.String.IndexOf%2A>-Methode verwendet, um die Punkte in einer Zeichenfolge zu finden. Anschließend wird die <xref:System.String.Substring%2A>-Methode verwendet, um vollständige Sätze zurückzugeben.

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a>Weitere Informationen

- [Grundlegende Zeichenfolgenvorgänge in .NET](basic-string-operations.md)
- [Reguläre Ausdrücke in .NET](regular-expressions.md)
- [Analysieren von Zeichenfolgen mithilfe von String.Split in C#](../../csharp/how-to/parse-strings-using-split.md)
