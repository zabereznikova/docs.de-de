---
title: "&#220;berpr&#252;fung der Lokalisierbarkeit | Microsoft Docs"
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
  - "Weltweit einsatzfähige Anwendungen, Lokalisierbarkeit"
  - "Anwendungsentwicklung [.NET Framework], Lokalisierung"
  - "Lokalisierbarkeit [.NET Framework]"
  - "Internationale Anwendungen [.NET Framework], Lokalisierbarkeit"
  - "Globalisierung [.NET Framework], Lokalisierbarkeit"
  - "Kultur, Lokalisierbarkeit"
  - "Lokalisierung [.NET Framework], Lokalisierbarkeit"
  - "Globale Anwendungen, Lokalisierbarkeit"
  - "Lokalisieren von Ressourcen"
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;berpr&#252;fung der Lokalisierbarkeit
Die Prüfung ist ein Zwischenschritt in der Entwicklung einer weltweit einsetzbaren Anwendung.  Sie überprüft, dass eine globalisierte Anwendung für die Lokalisierung bereit ist und identifiziert Code oder alle Aspekte der Benutzeroberfläche, die besondere Behandlung erfordern.  Dieser Schritt ist auch hilfreich, um sicherzustellen, dass während der Lokalisierung Funktionsfehler in die Anwendung integriert werden.  Wenn alle Probleme, die von der Prüfung ausgelöst werden, behandelt wurden, ist die Anwendung für die Lokalisierung bereit.  Wenn die Prüfung gründlich ist, Sie sollten während des Lokalisierungsprozesses keinerlei Quellcode ändern müssen.  
  
 Die Prüfung umfasst folgende drei Überprüfungen:  
  
-   [Werden die Globalisierungsempfehlungen implementiert?](#global)  
  
-   [Werden kulturabhängige Funktionen ordnungsgemäß behandelt?](#culture)  
  
-   [Haben Sie die Anwendung mit internationalen Daten getestet?](#test)  
  
<a name="global"></a>   
## Implementieren von Globalisierungsempfehlungen  
 Wenn Sie die Anwendung in Hinblick auf die Lokalisierung entworfen und entwickelt haben und wenn Sie den Empfehlungen befolgt haben, die im Artikel [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) erläutert werden, ist die Prüfung größtenteils einen Durchgang zur Qualitätssicherung dar.  Andernfalls dieser Phase sollten Sie die Empfehlungen für [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) überprüfen und implementieren Fehler im Quellcode suchen und beheben, die die Lokalisierung verhindern.  
  
<a name="culture"></a>   
## Arbeiten mit kulturabhängigen Funktionen  
 . .NET Framework bietet programmgesteuerte Unterstützung nicht in mehreren Bereichen, die weit von der Kultur unterscheiden.  In den meisten Fällen müssen Sie benutzerdefinierten Code zu den Handlefunktionsbereichen wie folgt schreiben:  
  
-   Adressen.  
  
-   Telefonnummern.  
  
-   Papierformate.  
  
-   Maßeinheiten verwendet für Längen, Gewichtungen, Bereich, Lautstärke und Temperaturen.  Obwohl .NET Framework keine integrierte Unterstützung zum Konvertieren zwischen Maßeinheiten bietet, können Sie die Eigenschaft <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=fullName> verwenden, um zu bestimmen, ob ein bestimmtes Land oder ein Bereich metrische das System verwendet, wie im folgenden Beispiel veranschaulicht.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## Testen der Anwendung  
 Bevor Sie eine Anwendung lokalisieren, sollten Sie diese testen, indem Sie internationale Daten in internationalen Betriebssystemen verwenden.  Obwohl die meisten der Benutzeroberfläche an dieser Stelle nicht lokalisiert werden, sind Sie in der Lage, Probleme wie folgt zu erkennen:  
  
-   Serialisierte Daten, die nicht richtig zu Betriebssystemversionen deserialisiert.  
  
-   Numerische Daten, die nicht die Konventionen der aktuellen Kultur übernommen.  Beispielsweise werden Zahlen mit fehlerhaften Gruppentrennzeichen, Dezimaltrennzeichen oder Währungssymbolen angezeigt werden.  
  
-   Datums\- und Uhrzeitdaten, die nicht die Konventionen der aktuellen Kultur übernommen.  Zum Beispiel können sich Zahlen, die darstellen Monat, Tag angezeigt wird und sich in der falschen Reihenfolge, Datumstrennzeichen falsch, oder Zeitzoneninformationen sind möglicherweise falsch.  
  
-   Ressourcen, die nicht gefunden werden können, da Sie keine Standardkultur für die Anwendung angegeben haben.  
  
-   Zeichenfolgen, die in einer ungewöhnlichen Reihenfolge für die spezifische Kultur angezeigt werden.  
  
-   Zeichenfolgenvergleiche oder Vergleiche auf Gleichheit Rückholunerwartete die ergebnisse.  
  
 Wenn Sie den Globalisierungsempfehlungen befolgt haben, wenn Sie die Anwendung ordnungsgemäß, wurde die Nicht\-Vorlagenfunktion kulturabhängige Funktionen entwickeln, und identifiziert und der Lokalisierung anspricht, die während der Tests entstanden, können Sie mit dem nächsten Schritt fortfahren, [Lokalisierung](../../../docs/standard/globalization-localization/localization.md).  
  
## Siehe auch  
 [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)   
 [Lokalisierung](../../../docs/standard/globalization-localization/localization.md)   
 [Globalisierung](../../../docs/standard/globalization-localization/globalization.md)   
 [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md)