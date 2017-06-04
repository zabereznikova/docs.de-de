---
title: "Escapezeichen in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Escapezeichen"
  - "Zeichen, Escapezeichen"
  - "Konstrukte, Escapezeichen"
  - "Escapezeichen"
  - "Reguläre Ausdrücke, Escapezeichen"
  - "Ersetzungsmuster"
  - "Zeichen ohne Escapezeichen"
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
caps.latest.revision: 31
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 29
---
# Escapezeichen in regul&#228;ren Ausdr&#252;cken
Der umgekehrte Schrägstrich \(\\\) in einem regulären Ausdruck kann für eine der folgenden Optionen stehen:  
  
-   Das darauf folgende Zeichen ist ein Sonderzeichen, wie in der Tabelle im folgenden Abschnitt gezeigt.  `\b` ist z. B. ein Anker, der angibt, dass die Übereinstimmung eines regulären Ausdrucks mit einer Wortgrenze beginnen sollte, `\t` stellt einen Tabulator dar und `\x020` stellt ein Leerzeichen dar.  
  
-   Ein Zeichen, das andernfalls als Sprachkonstrukt ohne Escapezeichen interpretiert werden würde, sollte als Zeichenliteral interpretiert werden.  Durch eine geschweifte Klammer \(`{`\) wird z. B. der Beginn der Definition eines Quantifizierers angezeigt, aber ein von einer geschweiften Klammer \(`\{`\) gefolgter umgekehrter Schrägstrich gibt an, dass das Modul für reguläre Ausdrücke eine Entsprechung für die geschweifte Klammer finden sollte.  Auf ähnliche Weise markiert ein einzelner umgekehrter Schrägstrich den Anfang eines Sprachkonstrukts mit Escapezeichen, aber zwei umgekehrte Schrägstriche \(`\\`\) geben an, dass das Modul für reguläre Ausdrücke eine Entsprechung für den umgekehrten Schrägstrich finden soll.  
  
> [!NOTE]
>  Escapezeichen werden in Mustern von regulären Ausdrücken, jedoch nicht in Ersetzungsmustern erkannt.  
  
## Escapezeichen in .NET Framework  
 In der folgenden Tabelle sind die Escapezeichen aufgeführt, die von regulären .NET Framework\-Ausdrücken unterstützt werden.  
  
|Zeichen oder Sequenz|Beschreibung|  
|--------------------------|------------------|  
|Alle Zeichen außer Folgenden:<br /><br /> .  $ ^ { \[ \( &#124; \) \* \+ ?  \\|Andere als die in der Spalte **Zeichen oder Sequenz** aufgelistete Zeichen haben keine spezielle Bedeutung in regulären Ausdrücken, sie stehen für sich selbst.<br /><br /> Die in der Spalte **Zeichen oder Sequenz** enthaltenen Zeichen sind spezielle Sprachelemente regulärer Ausdrücke.  Um diese in einem regulären Ausdruck zu vergleichen, müssen sie mit Escapezeichen versehen oder in eine [positive Zeichengruppe](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) einbezogen werden.  Der reguläre Ausdruck `\$\d+` oder `[$]\d+` entspricht z. B. "$1200".|  
|`\a`|Entspricht dem Klingelzeichen \(Warnsignal\) `\u0007`.|  
|`\b`|Entspricht in einer `[`*character\_group*`]`\-Zeichenklasse einem Rücktastenzeichen `\u0008`.  \(Siehe [Zeichenklassen](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).\) Außerhalb einer Zeichenklasse ist `\b` ein Anker, der einer Wortgrenze entspricht.  \(Siehe [Anchor](../../../docs/standard/base-types/anchors-in-regular-expressions.md).\)|  
|`\t`|Entspricht dem Tabstoppzeichen `\u0009`.|  
|`\r`|Entspricht dem Wagenrücklaufzeichen `\u000D`.  `\r` ist nicht mit dem Zeilenumbruchzeichen \(`\n`\) identisch.|  
|`\v`|Entspricht dem vertikalen Tabstoppzeichen `\u000B`.|  
|`\f`|Entspricht dem Seitenvorschubzeichen `\u000C`.|  
|`\n`|Entspricht einer neuen Zeile `\u000A`.|  
|`\e`|Entspricht dem Escapezeichen `\u001B`.|  
|`\` *nnn*|Findet eine Entsprechung für ein ASCII\-Zeichen, wobei *nnn* aus zwei oder drei Ziffern besteht, die den oktalen Zeichencode darstellen.  Beispielsweise stellt `\040` ein Leerzeichen dar.  Dieses Konstrukt wird als Rückverweis interpretiert, wenn es nur eine Ziffer \(z. B. `\2`\) hat oder wenn es der Nummer einer Erfassungsgruppe entspricht.  \(Siehe [Rückverweiskonstrukte](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).\)|  
|`\x` *nn*|Findet eine Entsprechung für ein ASCII\-Zeichen, wobei *nn* ein zweistelliger Hexadezimalzeichencode ist.|  
|`\c` *X*|Entspricht einem ASCII\-Steuerzeichen, wobei X der Buchstabe des Steuerzeichens ist.  Beispielsweise ist `\cC` STRG\+C.|  
|`\u` *nnnn*|Entspricht einer Codeeinheit UTF\-16 ab, deren Wert *nnnn* hexadezimal ist. **Note:**  Das Perl 5\-Escapezeichen zum Festlegen, dass Unicode von .NET Framework nicht unterstützt wird.  Das Perl 5\-Escape\-Zeichen hat das Format `\x{`*\#\#\#\#*`…}`, wobei *\#\#\#\#*`…` einer Reihe von Hexadezimalziffern entspricht.  Verwenden Sie stattdessen `\u`*nnnn*.|  
|`\`|Folgt diesem Zeichen ein Zeichen, das nicht als Escapezeichen erkannt wird, entspricht es diesem Zeichen.  `\*` entspricht beispielsweise einem Sternchen \(\*\) und ist gleich `\x2A`.|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von Escapezeichen in einem regulären Ausdruck.  Es analysiert eine Zeichenfolge, die die Namen der größten Orten der Welt und ihre Bevölkerungen in 2009 enthält.  Jeder Ortsname wird durch ein Tabstoppzeichen \(`\t`\) oder einen senkrechten Strich \(&#124; oder `\u007c`\) von seiner Einwohnerzahl getrennt.  Einzelne Orte und ihre Einwohnerzahlen werden durch einen Wagenrücklauf und einen Zeilenvorschub von einander getrennt.  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 Der reguläre Ausdruck `\G(.+)[\t|\u007c](../../../amples/snippets/visualbasic/VS_Snippets_Wpf/DocumentStructure/visualbasic/spec_withstructure-xps/_rels/.rels)\r?\n` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung|  
|------------|------------------|  
|`\G`|Beginnen Sie den Abgleich an der Stelle, wo der letzte Abgleich geendet hat.|  
|`(.+)`|Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen.  Dies ist die erste Erfassungsgruppe.|  
|`[\t\u007c]`|Entsprechung für einen Tabulator \(`\t`\) oder einen senkrechten Strich \(&#124;\).|  
|`(.+)`|Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen.  Dies ist die zweite Erfassungsgruppe.|  
|`\r?  \n`|Entspricht 0 \(Null\) oder einem Vorkommen des Wagenrücklaufs, gefolgt von einer neuen Zeile.|  
  
## Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)