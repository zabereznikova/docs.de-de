---
title: "Ausw&#228;hlen zwischen &quot;DateTime&quot;, &quot;DateTimeOffset&quot;, &quot;TimeSpan&quot; und &quot;TimeZoneInfo&quot; | Microsoft Docs"
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
  - "DateTimeOffset-Struktur"
  - "TimeZoneInfo-Klasse"
  - "Zeitzonen [.NET Framework], häufige Verwendungszwecke"
  - "Datums- und Uhrzeitklassen [.NET Framework]"
  - "Zeitzonen [.NET Framework], Typoptionen"
  - "DateTime-Struktur"
ms.assetid: 07f17aad-3571-4014-9ef3-b695a86f3800
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Ausw&#228;hlen zwischen &quot;DateTime&quot;, &quot;DateTimeOffset&quot;, &quot;TimeSpan&quot; und &quot;TimeZoneInfo&quot;
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]\-Anwendungen, die Datums\- und Uhrzeitinformationen verwenden, sind sehr vielfältig und können diese Informationen auf verschiedene Weise verwenden. Die häufigeren Verwendungsarten von Datums\- und Uhrzeitinformationen sind mindestens eine der folgenden:  
  
-   Darstellen eines reinen Datums, damit Zeitinformationen unberücksichtigt bleiben.  
  
-   Darstellen einer reinen Uhrzeit, damit Datumsinformationen unberücksichtigt bleiben.  
  
-   Darstellen eines abstrakten Datums mit Uhrzeit, die an keine bestimmte Zeit und keinen bestimmten Ort gebunden sind \(z. B. öffnen die meisten Geschäfte einer internationalen Kette an Wochentagen um 9:00 Uhr\).  
  
-   Abrufen von Datums\- und Uhrzeitinformationen aus Quellen außerhalb von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], typischerweise wo Datums\- und Uhrzeitinformationen in einem einfachen Datentyp gespeichert sind.  
  
-   Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Einige Anwendungen erfordern, dass ein Datum und eine Uhrzeit eindeutig sind, nur auf dem Hostsystem. Andere erfordern, dass sie über Systeme hinweg eindeutig sind \(d. h. ein auf dem einen System serialisiertes Datum kann weltweit auf einem anderen System sinnvoll deserialisiert und verwendet werden\).  
  
-   Erhalten mehrerer verwandter Zeiten \(z. B. die lokale Zeit des Anforderers und die Empfangszeit des Servers für eine Webanforderung\).  
  
-   Durchführen von Datums\- und Uhrzeitberechnungen, möglicherweise mit einem Ergebnis, das einen einzigen Zeitpunkt eindeutig identifiziert.  
  
 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] enthält die Typen <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan> und <xref:System.TimeZoneInfo>, die alle zum Erstellen von Anwendungen verwendet werden können, die mit Datumsangaben und Uhrzeiten arbeiten.  
  
> [!NOTE]
>  In diesem Thema wird kein vierter Typ, <xref:System.TimeZone>, behandelt, weil seine Funktionalität nahezu vollständig in der <xref:System.TimeZoneInfo>\-Klasse enthalten ist. Nach Möglichkeit sollten Entwickler die <xref:System.TimeZoneInfo>\-Klasse anstelle der <xref:System.TimeZone>\-Klasse verwenden.  
  
## Die DateTime\-Struktur  
 Ein <xref:System.DateTime>\-Wert definiert ein bestimmtes Datum und eine Uhrzeit. Ab Version 2.0 von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] enthält er eine <xref:System.DateTime.Kind%2A>\-Eigenschaft, die eingeschränkte Informationen über die Zeitzone bietet, zu der dieses Datum und die Uhrzeit gehören. Der von der <xref:System.DateTime.Kind%2A>\-Eigenschaft zurückgegebene <xref:System.DateTimeKind>Wert zeigt an, ob der <xref:System.DateTime>\-Wert eine lokale Uhrzeit darstellt \(<xref:System.DateTimeKind?displayProperty=fullName>\), eine Zeit im UTC\-Format \(Coordinated Universal Time\) \(<xref:System.DateTimeKind?displayProperty=fullName>\) oder eine unspezifische Uhrzeit \(<xref:System.DateTimeKind?displayProperty=fullName>\).  
  
 Die <xref:System.DateTime>\-Struktur eignet sich für Anwendungen, die Folgendes können:  
  
-   Nur mit Daten arbeiten.  
  
-   Nur mit Uhrzeiten arbeiten.  
  
-   Mit abstrakten Datums\- und Uhrzeitwerten arbeiten.  
  
-   Mit Datums\- und Uhrzeitwerten arbeiten, für die Zeitzoneninformationen fehlen.  
  
-   Nur mit UTC\-Datums\- und Uhrzeitwerten arbeiten.  
  
-   Datums\- und Uhrzeitinformationen aus Quellen außerhalb von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] abrufen, wie SQL\-Datenbanken. In der Regel speichern diese Quellen Datums\- und Uhrzeitinformationen in einem einfachen Format, das mit der <xref:System.DateTime>\-Struktur kompatibel ist.  
  
-   Arithmetische Operationen mit Datums\- und Uhrzeitwerten durchführen, wobei aber allgemeine Ergebnisse von Belang sind. Beispielsweise ist es bei einer Additionsoperation, bei der einem bestimmten Datum und einer Uhrzeit sechs Monate hinzuaddiert werden, oft nicht wichtig, ob das Ergebnis hinsichtlich der Sommerzeit angepasst wird.  
  
 Wenn nicht ein bestimmter <xref:System.DateTime>\-Wert UTC darstellt, ist dieser Datums\- und Uhrzeitwert häufig mehrdeutig oder in seiner Portierbarkeit eingeschränkt. Wenn z. B. ein <xref:System.DateTime>\-Wert die lokale Uhrzeit darstellt, ist er innerhalb dieser lokalen Zeitzone portierbar \(d. h., wenn der Wert auf einem anderen System in derselben Zeitzone deserialisiert wird, identifiziert dieser Wert immer noch eindeutig einen einzigen Zeitpunkt\). Außerhalb der lokalen Zeitzone kann dieser <xref:System.DateTime>\-Wert über mehrere Interpretationen verfügen. Wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft des Werts <xref:System.DateTimeKind?displayProperty=fullName> ist, ist er sogar noch weniger portierbar: Er ist jetzt innerhalb derselben Zeitzone mehrdeutig und möglicherweise sogar auf dem selben System, auf dem er erstmalig serialisiert wurde. Nur wenn ein <xref:System.DateTime>\-Wert eine UTC\-Zeit darstellt, identifiziert dieser Wert eindeutig einen einzigen Zeitpunkt, unabhängig vom System oder der Zeitzone, in der der Wert verwendet wird.  
  
> [!IMPORTANT]
>  Beim Speichern oder Freigeben von <xref:System.DateTime>\-Daten sollte UTC verwendet werden, und die <xref:System.DateTime>\-<xref:System.DateTime.Kind%2A>\-Eigenschaft des Werts sollte auf <xref:System.DateTimeKind?displayProperty=fullName> festgelegt werden.  
  
## Die DateTimeOffset\-Struktur  
 Die <xref:System.DateTimeOffset>\-Struktur stellt einen Datums\- und Uhrzeitwert zusammen mit einem Offset dar, der angibt, um wie viel dieser Wert von UTC abweicht. Somit identifiziert der Wert immer eindeutig einen einzigen Zeitpunkt.  
  
 Der <xref:System.DateTimeOffset>\-Typ bietet die gesamte Funktionalität des <xref:System.DateTime>\-Typs plus Unterstützung von Zeitzonen. Dadurch eignet er sich für Anwendungen, die Folgendes unterstützen:  
  
-   Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Der <xref:System.DateTimeOffset>\-Typ kann zur eindeutigen Definition der Bedeutung von "jetzt" verwendet werden, um Transaktionszeiten zu protokollieren, die Zeiten von System\- oder Anwendungsereignissen zu protokollieren und um die Zeiten der Erstellung und Änderung von Dateien aufzuzeichnen.  
  
-   Ausführen von allgemeinen Datums\- und Uhrzeitberechnungen  
  
-   Erhalten mehrerer verwandter Uhrzeiten, solange diese Zeiten als zwei gesonderte Werte oder als zwei Member einer Struktur gespeichert werden.  
  
> [!NOTE]
>  Diese Verwendungsarten für <xref:System.DateTimeOffset>\-Werte sind sehr viel häufiger als die für <xref:System.DateTime>\-Werte. Demzufolge sollte <xref:System.DateTimeOffset> als Standardtyp für Datum und Uhrzeit für die Anwendungsentwicklung angesehen werden.  
  
 Ein <xref:System.DateTimeOffset>\-Wert ist nicht an eine bestimmte Zeitzone gebunden, kann aber aus jeder der zahlreichen Zeitzonen stammen. Um dies zu veranschaulichen, listet das folgende Beispiel die Zeitzonen auf, zu denen eine Reihe von <xref:System.DateTimeOffset>\-Werten \(einschließlich eines Werts in lokaler Pacific Normalzeit\) gehören können.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual1.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual1.vb#1)]  
  
 Die Ausgabe zeigt, dass jeder Datums\- und Uhrzeitwert in diesem Beispiel zu mindestens drei verschiedenen Zeitzonen gehören kann. Der <xref:System.DateTimeOffset>\-Wert "6\/10\/2007" zeigt, dass, wenn ein Datums\- und Uhrzeitwert eine Sommerzeit darstellt, sein Offset von UTC noch nicht einmal unbedingt dem UTC\-Basisoffset der Ursprungszeitzone oder dem in seinem Anzeigenamen vorgefundenen Offset von UTC entsprechen muss. Dies bedeutet, dass, weil ein einzelner <xref:System.DateTimeOffset>\-Wert nicht eng mit seiner Zeitzone verknüpft ist, er nicht den Übergang einer Zeitzone zur und aus der Sommerzeit wiedergeben kann. Dies kann besonders problematisch sein, wenn ein <xref:System.DateTimeOffset>\-Wert mithilfe von Datums\- und Uhrzeitberechnungen manipuliert wird. \(Eine Erläuterung der Durchführung von Datums\- und Uhrzeitberechnungen auf eine Weise, die die Anpassungsregeln einer Zeitzone berücksichtigt, finden Sie unter [Durchführen arithmetischer Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md).\)  
  
## Die TimeSpan\-Struktur  
 Die <xref:System.TimeSpan>\-Struktur stellt ein Zeitintervall dar. Sein zwei typischen Anwendungsmöglichkeiten sind:  
  
-   Darstellen des Zeitintervalls zwischen zwei Datums\- und Uhrzeitwerten. Beispielsweise gibt die Subtraktion eines <xref:System.DateTime>\-Werts von einem anderen einen <xref:System.TimeSpan>\-Wert zurück.  
  
-   Messen der verstrichenen Zeit. Beispielsweise gibt die <xref:System.Diagnostics.Stopwatch.Elapsed%2A?displayProperty=fullName>\-Eigenschaft einen <xref:System.TimeSpan>\-Wert zurück, der das Zeitintervall angibt, das seit dem Aufrufen einer der <xref:System.Diagnostics.Stopwatch>\-Methoden, die verstrichene Zeit zu messen beginnen, verstrichen ist.  
  
 Ein <xref:System.TimeSpan>\-Wert kann auch als Ersatz für einen <xref:System.DateTime>\-Wert verwendet werden, wenn dieser Wert eine Uhrzeit ohne Verweis auf eine bestimmte Tageszeit widerspiegelt. Diese Verwendung ähnelt den Eigenschaften <xref:System.DateTime.TimeOfDay%2A?displayProperty=fullName> und <xref:System.DateTimeOffset.TimeOfDay%2A?displayProperty=fullName>, die einen <xref:System.TimeSpan>\-Wert zurückgeben, der die Uhrzeit ohne Verweis auf ein Datum darstellt. Beispielsweise kann die <xref:System.TimeSpan>\-Struktur verwendet werden, um die täglichen Öffnungszeiten eines Geschäfts darzustellen oder um die Uhrzeit darzustellen, zu der alle regulären Ereignisse auftreten.  
  
 Das folgende Beispiel definiert eine `StoreInfo`\-Struktur, die <xref:System.TimeSpan>\-Objekte für Öffnungszeiten von Geschäften enthält sowie ein <xref:System.TimeZoneInfo>\-Objekt, das die Zeitzone des Geschäfts darstellt. Die Struktur enthält außerdem zwei Methoden, `IsOpenNow` und `IsOpenAt`, die angeben, ob das Geschäft zu einem vom Benutzer angegebenen Zeitpunkt geöffnet ist, wobei angenommen wird, dass er sich in der lokalen Zeitzone aufhält.  
  
 [!code-csharp[Conceptual.ChoosingDates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.choosingdates/cs/datetimereplacement1.cs#1)]
 [!code-vb[Conceptual.ChoosingDates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.choosingdates/vb/datetimereplacement1.vb#1)]  
  
 Die `StoreInfo`\-Struktur kann dann von Clientcode wie folgt verwendet werden.  
  
 [!code-csharp[Conceptual.ChoosingDates#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.choosingdates/cs/datetimereplacement1.cs#2)]
 [!code-vb[Conceptual.ChoosingDates#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.choosingdates/vb/datetimereplacement1.vb#2)]  
  
## Die TimeZoneInfo\-Klasse  
 Die <xref:System.TimeZoneInfo>\-Klasse stellt eine beliebige Zeitzone der Erde dar und ermöglicht die Konvertierung jeglicher Datums\- und Uhrzeitwerte in einer in die entsprechenden Werte in einer anderen Zeitzone. Die <xref:System.TimeZoneInfo>\-Klasse ermöglicht das Arbeiten mit Datums\- und Zeitwerten, sodass jeder Datums\- und Uhrzeitwert eindeutig einen einzigen Zeitpunkt identifiziert. Die <xref:System.TimeZoneInfo>\-Klasse ist außerdem erweiterbar. Obwohl sie von den für Windows\-Systeme bereitgestellten und in der Registrierung definierten Zeitzoneninformationen abhängt, unterstützt sie die Erstellung benutzerdefinierter Zeitzonen. Sie unterstützt außerdem die Serialisierung und Deserialisierung von Zeitzoneninformationen.  
  
 In einigen Fällen kann noch weitere Entwicklungsarbeit erforderlich sein, um die <xref:System.TimeZoneInfo>\-Klasse optimal zu nutzen. Erstens sind Datums\-und Uhrzeitwerte nicht eng mit den Zeitzonen verknüpft, zu denen sie gehören. Daher kann die Zuordnung eines Datums\- und Uhrzeitwerts zu seiner Zeitzone leicht aufgehoben werden, wenn Ihre Anwendung nicht einen Mechanismus bereitstellt, um ein Datum und eine Uhrzeit mit der zugehörigen Zeitzone zu verknüpfen. \(Eine Methode zum Verknüpfen dieser Informationen besteht darin, eine Klasse oder Struktur zu definieren, die sowohl den Datums\- und Zeitwert als auch sein zugeordnetes Zeitzonenobjekt enthält.\) Zweitens besitzen Windows XP und frühere Versionen von Windows keine echte Unterstützung für historische Zeitzoneninformationen, und [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] verfügt nur über eingeschränkte Unterstützung. Anwendungen, die darauf ausgelegt sind, historische Datums\- und Uhrzeitwerte zu verarbeiten, müssen in hohem Maße benutzerdefinierte Zeitzonen einsetzen.  
  
 Die Zeitzonenunterstützung in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] kann nur genutzt werden, wenn die Zeitzone, zu der ein Datums\- und Uhrzeitwert gehört, bekannt ist, wenn das Datums\- und Uhrzeitobjekt instanziiert wird. Dies ist häufig nicht der Fall, insbesondere bei Web\-oder Netzwerkanwendungen.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)