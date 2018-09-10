---
title: Überprüfung der Lokalisierbarkeit
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b19bc78f44781923df6873ccc9720f4605731976
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206061"
---
# <a name="localizability-review"></a>Überprüfung der Lokalisierbarkeit
Die Überprüfung der Lokalisierbarkeit ist ein Zwischenschritt bei der Entwicklung einer weltweit einsetzbaren Anwendung. Dabei wird überprüft, ob eine globalisierte Anwendung für die Lokalisierung bereit ist, und es werden Code oder Aspekte der Benutzeroberfläche bezeichnet, die eine besondere Behandlung erfordern. Mit diesem Schritt wird zudem sichergestellt, dass beim Lokalisierungsprozess keine Funktionsfehler in Ihrer Anwendung auftreten. Wenn Sie alle Probleme behoben haben, die bei der Überprüfung der Lokalisierbarkeit ausgelöst wurden, ist Ihre Anwendung für die Lokalisierung bereit. Bei einer gründlichen Überprüfung der Lokalisierbarkeit sollten Sie beim Lokalisierungsprozess nicht den Quellcode ändern müssen.  
  
 Die Überprüfung der Lokalisierbarkeit umfasst die folgenden drei Prüfungen:  
  
-   [Wurden die Globalisierungsempfehlungen implementiert?](#global)  
  
-   [Wurden kulturabhängige Features ordnungsgemäß behandelt?](#culture)  
  
-   [Haben Sie Ihre Anwendung mit internationalen Daten getestet?](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a>Implementieren von Globalisierungsempfehlungen  
 Wenn Sie Ihre Anwendung unter Berücksichtigung einer späteren Lokalisierung entworfen und entwickelt und dabei die im Artikel [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) erläuterten Empfehlungen befolgt haben, sollte Ihre Anwendung der Überprüfung der Lokalisierbarkeit hinsichtlich der Qualitätssicherung größtenteils standhalten. Andernfalls sollten Sie an dieser Stelle die Empfehlungen hinsichtlich einer [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) lesen und implementieren und die Fehler im Quellcode, die eine Lokalisierung unmöglich machen, beheben.  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a>Arbeiten mit kulturabhängigen Funktionen  
 Das .NET Framework bietet keine programmgesteuerte Unterstützung für viele Bereiche, die je nach Kultur variieren. In den meisten Fällen müssen Sie benutzerdefinierten Code schreiben, um Featurebereiche wie folgt zu behandeln:  
  
-   Adressen  
  
-   Telefonnummern  
  
-   Papierformate  
  
-   Maßeinheiten für Länge, Gewicht, Fläche, Volumen und Temperatur. Obwohl das .NET Framework keine integrierte Unterstützung für die Konvertierung von Maßeinheiten bietet, können Sie anhand der <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType>-Eigenschaft feststellen, ob ein bestimmtes Land oder eine Region das metrische System verwendet. Dies wird im folgenden Beispiel veranschaulicht.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a>Testen der Anwendung  
 Vor der Lokalisierung Ihrer Anwendung sollten Sie sie mit internationalen Daten und internationalen Betriebssystemversionen testen. Obwohl der Großteil der Benutzeroberfläche zu diesem Zeitpunkt nicht lokalisiert ist, können Sie Probleme wie die folgenden erkennen:  
  
-   Serialisierte Daten, die in verschiedenen Betriebssystemversionen nicht korrekt deserialisiert werden  
  
-   Numerische Daten, die nicht den Konventionen der aktuellen Kultur entsprechen. Beispiel: Zahlen werden möglicherweise mit ungenauen Gruppentrennzeichen, Dezimaltrennzeichen oder Währungssymbolen angezeigt werden.  
  
-   Datums- und Uhrzeitangaben, die nicht den Konventionen der aktuellen Kultur entsprechen. Beispiel: Zahlen für Monat und Tag werden möglicherweise in der falschen Reihenfolge angezeigt, Datumstrennzeichen werden evtl. falsch angezeigt oder die Zeitzoneninformationen sind möglicherweise falsch.  
  
-   Ressourcen, die nicht gefunden werden können, weil Sie keine Standardkultur für Ihre Anwendung festgelegt haben  
  
-   Zeichenfolgen, die in einer für die spezifische Kultur ungewöhnlichen Reihenfolge angezeigt werden  
  
-   Zeichenfolgenvergleiche oder Vergleiche im Hinblick auf Gleichheit, die unerwartete Ergebnisse zurückgeben  
  
 Wenn Sie bei der Anwendungsentwicklung die Globalisierungsempfehlungen befolgt, kulturabhängige Features ordnungsgemäß behandelt und im Zuge von Tests Lokalisierungsprobleme ermittelt und behoben haben, können Sie mit dem nächsten Schritt der [Lokalisierung](../../../docs/standard/globalization-localization/localization.md) fortfahren.  
  
## <a name="see-also"></a>Siehe auch

- [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)  
- [Lokalisierung](../../../docs/standard/globalization-localization/localization.md)  
- [Globalisierung](../../../docs/standard/globalization-localization/globalization.md)  
- [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
