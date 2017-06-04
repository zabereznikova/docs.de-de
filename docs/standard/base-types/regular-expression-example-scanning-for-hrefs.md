---
title: "Beispiel f&#252;r regul&#228;re Ausdr&#252;cke: Suchen nach HREFs | Microsoft Docs"
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
  - "Suchen mit regulären Ausdrücken, Beispiele"
  - "Analysieren von Text mit regulären Ausdrücken, Beispiele"
  - "Reguläre Ausdrücke, Beispiele"
  - "Reguläre Ausdrücke von .NET Framework, Beispiele"
  - "Reguläre Ausdrücke [.NET Framework], Beispiele"
  - "Musterabgleich mit regulären Ausdrücken, Beispiele"
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# Beispiel f&#252;r regul&#228;re Ausdr&#252;cke: Suchen nach HREFs
Im folgenden Beispiel wird eine Eingabezeichenfolge durchsucht und zeigt alle Vorkommnisse von href\="..." an Werte und ihre Positionen in der Zeichenfolge.  
  
## Das Regex\-Objekt  
 Da die `DumpHRefs`\-Methode mehrfach im Benutzercode aufgerufen werden kann, wird die `static` \(`Shared` in Visual Basic\) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>\-Methode verwendet.  Dies ermöglich dem Modul für reguläre Ausdrücke, den regulären Ausdruck zwischenzuspeichern, und vermeidet den zusätzlichen Aufwand, jedesmal ein neues <xref:System.Text.RegularExpressions.Regex>\-Objekt zu instanziieren, wenn die Methode aufgerufen wird.  Ein <xref:System.Text.RegularExpressions.Match>\-Objekt wird dann verwendet, um alle Übereinstimmungen in der Zeichenfolge zu durchlaufen.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 Im folgenden Beispiel wird der Aufruf der `DumpHRefs`\-Methode veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 Das Muster für reguläre Ausdrücke `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`href`|Sucht nach der Literalzeichenfolge "href".  Die Groß\- und Kleinschreibung wird bei der Übereinstimmung nicht berücksichtigt.|  
|`\s*`|Sucht nach 0 \(null\) oder mehr Leerzeichen.|  
|`=`|Sucht nach dem Gleichheitszeichen.|  
|`\s*`|Sucht nach 0 \(null\) oder mehr Leerzeichen.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Sucht nach einer der folgenden Zeichenkombinationen, ohne das Ergebnis einer erfassten Gruppe zuzuweisen:<br /><br /> -   Ein Anführungszeichen oder Apostroph, gefolgt von keinem oder mehreren Vorkommen eines beliebigen Zeichens ein Anführungszeichen oder ein Apostroph, gefolgt von einem Anführungszeichen oder ein Apostroph.  Die Gruppe mit dem Namen `1` ist in diesem Muster enthalten.<br />-   Ein oder mehr Nicht\-Leerzeichen.  Die Gruppe mit dem Namen `1` ist in diesem Muster enthalten.|  
|`(?<1>[^"']*)`|Weisen Sie null\) oder mehr Vorkommen eines beliebigen Zeichens ein Anführungszeichen oder ein Apostroph der Erfassungsgruppe mit dem Namen `1`.|  
|`"(?<1>\S+)`|Weist ein oder mehr Nicht\-Leerzeichen der Erfassungsgruppe mit dem Namen `1` zu.|  
  
## Suchergebnisklasse  
 Die Ergebnisse einer Suche werden in der <xref:System.Text.RegularExpressions.Match>\-Klasse gespeichert, die Zugriff auf alle von der Suche extrahierten Teilzeichenfolgen bietet.  Die durchsuchte Zeichenfolge und der verwendete reguläre Ausdruck werden ebenfalls gespeichert, sodass die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=fullName>\-Methode aufgerufen werden kann, um einen weiteren Suchvorgang ab der Stelle auszuführen, an der der letzte Suchvorgang beendet wurde.  
  
## Explizit benannte Aufzeichnungen  
 In herkömmlichen regulären Ausdrücken werden umschließende Klammern automatisch nach der Reihenfolge durchnummeriert.  Daraus ergeben sich zwei Probleme:  Zum einen muss nach dem Hinzufügen oder Entfernen von Klammern der gesamte Code, der sich auf die numerierten Klammern bezieht, gemäß der neuen Numerierung verändert werden.  Zweitens werden häufig unterschiedliche Klammerpaare verwendet, um zwei Alternativausdrücke für eine Übereinstimmung zu erhalten. Dadurch wird es schwierig festzustellen, durch welchen der beiden Ausdrücke das Ergebnis zurückgegeben wurde.  
  
 Um diesen Schwierigkeiten zu begegnen, unterstützt die <xref:System.Text.RegularExpressions.Regex>\-Klasse die `(?<name>…)`\-Syntax zur Speicherung einer Zeichenfolge in einem festgelegten Slot. \(Der Slot kann mit Zeichenfolgen oder ganzen Zahlen benannt werden; ganze Zahlen können schneller aufgerufen werden.\)  Damit können alle Suchergebnisse für dieselbe Zeichenfolge am gleichen Ort abgelegt werden.  Im Fall eines Konflikts ist das zuletzt im Slot gespeicherte Suchergebnis gültig. \(Eine vollständige Liste von mehrfachen Übereinstimmungen für einen einzelnen Slot steht jedoch zur Verfügung.\)  Ausführliche Informationen finden Sie den Ausführungen zur <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=fullName>\-Auflistung.  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)