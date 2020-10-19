---
title: Escapezeichen in regulären .NET-Ausdrücken
description: Erfahren Sie mehr über Sonderzeichen und Escapezeichen in regulären .NET-Ausdrücken.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unescaped characters
- replacement patterns
- characters, escapes
- regular expressions, character escapes
- escape characters
- .NET Framework regular expressions, character escapes
- constructs, character escapes
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
ms.openlocfilehash: 4491b83db195a8d0f5bbf4f4326d92ed9ebd24e7
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050441"
---
# <a name="character-escapes-in-regular-expressions"></a>Escapezeichen in regulären Ausdrücken
Der umgekehrte Schrägstrich (\\) in einem regulären Ausdruck kann für eine der folgenden Optionen stehen:  
  
- Das darauf folgende Zeichen ist ein Sonderzeichen, wie in der Tabelle im folgenden Abschnitt gezeigt. `\b` ist z. B. ein Anker, der angibt, dass die Übereinstimmung eines regulären Ausdrucks mit einer Wortgrenze beginnen sollte, `\t` stellt einen Tabulator dar und `\x020` stellt ein Leerzeichen dar.  
  
- Ein Zeichen, das andernfalls als Sprachkonstrukt ohne Escapezeichen interpretiert werden würde, sollte als Zeichenliteral interpretiert werden. Durch eine geschweifte Klammer (`{`) wird z. B. der Beginn der Definition eines Quantifizierers angezeigt, aber ein von einer geschweiften Klammer (`\{`) gefolgter umgekehrter Schrägstrich gibt an, dass die Engine für reguläre Ausdrücke eine Entsprechung für die geschweifte Klammer finden sollte. Auf ähnliche Weise markiert ein einzelner umgekehrter Schrägstrich den Anfang eines Sprachkonstrukts mit Escapezeichen, aber zwei umgekehrte Schrägstriche (`\\`) geben an, dass die Engine für reguläre Ausdrücke eine Entsprechung für den umgekehrten Schrägstrich finden soll.  
  
> [!NOTE]
> Escapezeichen werden in Mustern von regulären Ausdrücken, jedoch nicht in Ersetzungsmustern erkannt.  
  
## <a name="character-escapes-in-net"></a>Escapezeichen in .NET  
 In der folgenden Tabelle sind die Escapezeichen aufgeführt, die von regulären Ausdrücken in .NET unterstützt werden.  
  
|Zeichen oder Sequenz|Beschreibung|  
|---------------------------|-----------------|  
|Alle Zeichen außer Folgenden:<br /><br /> . $ ^ { [ ( &#124; ) * + ? \ |Andere als die in der Spalte **Zeichen oder Sequenz** aufgelistete Zeichen haben keine spezielle Bedeutung in regulären Ausdrücken, sie stehen für sich selbst.<br /><br /> Die in der Spalte **Zeichen oder Sequenz** enthaltenen Zeichen sind spezielle Sprachelemente regulärer Ausdrücke. Um diese in einem regulären Ausdruck abzugleichen, müssen sie mit Escapezeichen versehen oder in eine [positive Zeichengruppe](character-classes-in-regular-expressions.md) einbezogen werden. Der reguläre Ausdruck `\$\d+` oder `[$]\d+` entspricht z. B. "$1200".|  
|`\a`|Entspricht dem Klingelzeichen (Warnsignal) `\u0007`.|  
|`\b`|Entspricht in einer `[`*Zeichengruppe*`]`-Zeichenklasse einem Rücktastenzeichen `\u0008`.  (Siehe [Zeichenklassen](character-classes-in-regular-expressions.md).) Außerhalb einer Zeichenklasse ist `\b` ein Anker, der einer Wortgrenze entspricht. (Siehe [Anker](anchors-in-regular-expressions.md).)|  
|`\t`|Entspricht dem Tabstoppzeichen `\u0009`.|  
|`\r`|Entspricht dem Wagenrücklaufzeichen `\u000D`. `\r` ist nicht mit dem Zeilenumbruchzeichen (`\n`) identisch.|  
|`\v`|Entspricht dem vertikalen Tabstoppzeichen `\u000B`.|  
|`\f`|Entspricht dem Seitenvorschubzeichen `\u000C`.|  
|`\n`|Entspricht einer neuen Zeile `\u000A`.|  
|`\e`|Entspricht dem Escapezeichen `\u001B`.|  
|`\` *nnn*|Entspricht einem ASCII-Zeichen, wobei *nnn* aus zwei oder drei Ziffern besteht, die den oktalen Zeichencode darstellen. Beispielsweise stellt `\040` ein Leerzeichen dar. Dieses Konstrukt wird als Rückverweis interpretiert, wenn es nur eine Ziffer (z. B. `\2`) hat oder wenn es der Nummer einer Erfassungsgruppe entspricht. (Siehe [Rückverweiskonstrukte](backreference-constructs-in-regular-expressions.md).)|  
|`\x` *nn*|Entspricht einem ASCII-Zeichen, wobei *nn* ein zweistelliger Hexadezimalzeichencode ist.|  
|`\c` *X*|Entspricht einem ASCII-Steuerzeichen, wobei X der Buchstabe des Steuerzeichens ist. Beispielsweise ist `\cC` STRG+C.|  
|`\u` *nnnn*|Entspricht einer UTF-16-Codeeinheit, deren Wert *nnnn* hexadezimal ist. **Hinweis**:  Das Perl 5-Escapezeichen, das zum Festlegen von Unicode verwendet wird, wird nicht von .NET unterstützt. Das Perl 5-Escape-Zeichen hat das Format `\x{` *####* `…}`, wobei *####* `…` einer Reihe von Hexadezimalziffern entspricht. Verwenden Sie stattdessen `\u`*nnnn*.|  
|`\`|Folgt diesem Zeichen ein Zeichen, das nicht als Escapezeichen erkannt wird, entspricht es diesem Zeichen. `\*` entspricht beispielsweise einem Sternchen (*) und ist gleich `\x2A`.|  
  
## <a name="an-example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von Escapezeichen in einem regulären Ausdruck. Es analysiert eine Zeichenfolge, die die Namen der größten Städte der Welt und deren Einwohnerzahlen im Jahr 2009 enthält. Jeder Ortsname wird durch ein Tabstoppzeichen (`\t`) oder einen senkrechten Strich (&#124; oder `\u007c`) von seiner Einwohnerzahl getrennt. Einzelne Orte und ihre Einwohnerzahlen werden durch einen Wagenrücklauf und einen Zeilenvorschub von einander getrennt.  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 Der reguläre Ausdruck `\G(.+)[\t\u007c](.+)\r?\n` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\G`|Beginnen Sie den Abgleich an der Stelle, wo der letzte Abgleich geendet hat.|  
|`(.+)`|Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen. Dies ist die erste Erfassungsgruppe.|  
|`[\t\u007c]`|Entspricht einem Tabulator (`\t`) oder einem senkrechten Strich (&#124;).|  
|`(.+)`|Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen. Dies ist die zweite Erfassungsgruppe.|  
|`\r?\n`|Entspricht 0 (Null) oder einem Vorkommen des Wagenrücklaufs, gefolgt von einer neuen Zeile.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
