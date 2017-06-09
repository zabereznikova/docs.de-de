---
title: "Instanziieren eines &quot;DateTimeOffset&quot;-Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Instanziierung von Zeitzonenobjekten"
  - "Zeitzonenobjekte [.NET Framework], Instanziierung"
  - "„DateTimeOffset“-Struktur, Konvertierung in DateTime"
  - "„DateTimeOffset“-Struktur, Instanziierung"
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Instanziieren eines &quot;DateTimeOffset&quot;-Objekts
Die <xref:System.DateTimeOffset>\-Struktur bietet mehrere Möglichkeiten, neue <xref:System.DateTimeOffset>\-Werte zu erstellen.  Viele dieser Möglichkeiten stimmen direkt mit den Methoden zum Instanziieren neuer <xref:System.DateTime>\-Werte überein, ermöglichen für die Datums\- und Uhrzeitwerte jedoch zusätzlich die Angabe eines Offsets von der koordinierten Weltzeit \(UTC\).  Zum Instanziieren eines <xref:System.DateTimeOffset>\-Werts sind insbesondere die folgenden Methoden verfügbar:  
  
-   Verwenden eines Datums\- und Uhrzeitliterals  
  
-   Aufrufen eines <xref:System.DateTimeOffset>\-Konstruktors  
  
-   Implizites Konvertieren eines Werts in einen <xref:System.DateTimeOffset>\-Wert  
  
-   Analysieren der Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts  
  
 Dieses Thema enthält detaillierte Informationen und Codebeispiele zum Instanziieren neuer <xref:System.DateTimeOffset>\-Werte mit diesen Methoden.  
  
## Datums\- und Uhrzeitliterale  
 Eine der gebräuchlichsten Methoden zum Instanziieren eines <xref:System.DateTime>\-Werts ist es, den Datums\- und Uhrzeitwert als hartcodierten Literalwert bereitzustellen, sofern dies von der jeweiligen Sprache unterstützt wird.  Mit dem folgenden Visual Basic\-Code wird z. B. ein <xref:System.DateTime>\-Objekt mit dem Wert 1. Januar 2008, 10:00 Uhr erstellt.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]  
  
 <xref:System.DateTimeOffset>\-Werte können ebenfalls mit Datums\- und Uhrzeitliteralen initialisiert werden, wenn die verwendeten Sprachen <xref:System.DateTime>\-Literale unterstützen.  Mit dem folgenden Visual Basic\-Code wird z. B. ein <xref:System.DateTimeOffset>\-Objekt erstellt.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]  
  
 Wie die Konsolenausgabe zeigt, wird dem auf diese Weise erstellten <xref:System.DateTimeOffset>\-Wert der Offset der lokalen Zeitzone zugewiesen.  Das bedeutet, dass ein mit einem Zeichenliteral zugewiesener <xref:System.DateTimeOffset>\-Wert keinen bestimmten Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.  
  
## "DateTimeOffset"\-Konstruktoren  
 Der <xref:System.DateTimeOffset>\-Typ definiert sechs Konstruktoren.  Vier von ihnen entsprechen <xref:System.DateTime>\-Konstruktoren mit einem zusätzlichen Parameter vom Typ <xref:System.TimeSpan>, der den Offset des Datums\- und Uhrzeitwerts von der koordinierten Weltzeit definiert.  Sie ermöglichen Ihnen die Definition eines <xref:System.DateTimeOffset>\-Werts auf Basis der Werte seiner einzelnen Datums\- und Uhrzeitkomponenten.  Im folgenden Code werden diese vier Konstruktoren z. B. zum Instanziieren von <xref:System.DateTimeOffset>\-Objekten mit den identischen Werten 7\/1\/2008 12:05 AM \+01:00 verwendet.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]  
  
 Beachten Sie, dass wenn der Wert des <xref:System.DateTimeOffset>\-Objekts, das mit einem <xref:System.Globalization.PersianCalendar>\-Objekt als eines der Argumente für dessen Konstruktor instanziiert wird, auf der Konsole angezeigt wird, dieser als Datum im gregorianischen Kalender und nicht als Datum im persischen Kalender ausgedrückt wird.  Ein Beispiel zur Ausgabe eines Datums mit dem persischen Kalender finden Sie im Thema <xref:System.Globalization.PersianCalendar>.  
  
 Mit den anderen beiden Konstruktoren wird ein <xref:System.DateTimeOffset>\-Objekt aus einem <xref:System.DateTime>\-Wert erstellt.  Der erste verfügt über einen einzigen Parameter, dem <xref:System.DateTime>\-Wert zum Konvertieren in einen <xref:System.DateTimeOffset>\-Wert.  Der Offset des resultierenden <xref:System.DateTimeOffset>\-Werts hängt von der <xref:System.DateTime.Kind%2A>\-Eigenschaft des einzigen Parameters des Konstruktors ab.  Wenn der Wert <xref:System.DateTimeKind?displayProperty=fullName> lautet, entspricht der Offset <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Andernfalls entspricht der Offset dem der lokalen Zeitzone.  Das folgende Beispiel zeigt die Verwendung dieses Konstruktors zum Instanziieren von <xref:System.DateTimeOffset>\-Objekten, die die koordinierte Weltzeit und die lokale Zeitzone darstellen:  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]  
  
> [!NOTE]
>  Das Aufrufen der Überladung des <xref:System.DateTimeOffset>\-Konstruktors, der über einen einzigen <xref:System.DateTime>\-Parameter verfügt, entspricht dem impliziten Konvertieren eines <xref:System.DateTime>\-Werts in einen <xref:System.DateTimeOffset>\-Wert.  
  
 Der zweite Konstruktor, der ein <xref:System.DateTimeOffset>\-Objekt aus einem <xref:System.DateTime>\-Wert erstellt, verfügt über zwei Parameters: den zu konvertierenden <xref:System.DateTime>\-Wert und einen <xref:System.TimeSpan>\-Wert, der den Offset des Datums\- und Uhrzeitwerts von der koordinierten Weltzeit darstellt.  Dieser Offsetwert muss der <xref:System.DateTime.Kind%2A>\-Eigenschaft des ersten Parameters des Konstruktors entsprechen. Andernfalls wird eine <xref:System.ArgumentException> ausgelöst.  Wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft des ersten Parameters <xref:System.DateTimeKind?displayProperty=fullName> lautet, muss der Wert des zweiten Parameters <xref:System.TimeSpan.Zero?displayProperty=fullName> entsprechen.  Wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft des ersten Parameters <xref:System.DateTimeKind?displayProperty=fullName> lautet, muss der Wert des zweiten Parameters dem Offset der lokalen Zeitzone entsprechen.  Wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft des ersten Parameters <xref:System.DateTimeKind?displayProperty=fullName> lautet, kann der Offset einem beliebigen gültigen Wert entsprechen.  Der folgende Code zeigt Aufrufe dieses Konstruktors zum Konvertieren von <xref:System.DateTime>\-Werten in <xref:System.DateTimeOffset>\-Werte.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]  
  
## Implizite Typkonvertierung  
 Der <xref:System.DateTimeOffset>\-Typ unterstützt eine implizite Typkonvertierung: von einem <xref:System.DateTime>\-Wert in einen <xref:System.DateTimeOffset>\-Wert. Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, die keine explizite Typumwandlung \(in C\#\) oder Konvertierung \(in Visual Basic\) erfordert und bei der keine Informationen verloren gehen.  Sie ermöglicht Code wie den folgenden:  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]  
  
 Der Offset des resultierenden <xref:System.DateTimeOffset>\-Werts hängt vom Wert der <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaft ab.  Wenn der Wert <xref:System.DateTimeKind?displayProperty=fullName> lautet, entspricht der Offset <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Wenn der Wert <xref:System.DateTimeKind?displayProperty=fullName> oder <xref:System.DateTimeKind?displayProperty=fullName> lautet, entspricht der Offset dem der lokalen Zeitzone.  
  
## Analysieren der Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts  
 Der <xref:System.DateTimeOffset>\-Typ unterstützt vier Methoden zur Konvertierung der Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts in einen <xref:System.DateTimeOffset>\-Wert:  
  
-   Die <xref:System.DateTimeOffset.Parse%2A>\-Methode, die versucht, die Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts in einen <xref:System.DateTimeOffset>\-Wert zu konvertieren, und eine Ausnahme auslöst, wenn die Konvertierung fehlschlägt.  
  
-   Die <xref:System.DateTimeOffset.TryParse%2A>\-Methode, die versucht, die Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts in einen <xref:System.DateTimeOffset>\-Wert zu konvertieren, und `false` zurückgibt, wenn die Konvertierung fehlschlägt.  
  
-   Die <xref:System.DateTimeOffset.ParseExact%2A>\-Methode, die versucht, die Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts in einem angegebenen Format in einen <xref:System.DateTimeOffset>\-Wert zu konvertieren.  Die Methode löst eine Ausnahme aus, wenn die Konvertierung fehlschlägt.  
  
-   Die <xref:System.DateTimeOffset.TryParseExact%2A>\-Methode, die versucht, die Zeichenfolgendarstellung eines Datums\- und Uhrzeitwerts in einem angegebenen Format in einen <xref:System.DateTimeOffset>\-Wert zu konvertieren.  Die Methode gibt `false` zurück, wenn die Konvertierung fehlschlägt.  
  
 Das folgende Beispiel zeigt Aufrufe dieser vier Konvertierungsmethoden zum Instanziieren eines <xref:System.DateTimeOffset>\-Werts.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)