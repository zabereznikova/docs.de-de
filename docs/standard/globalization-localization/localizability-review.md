---
title: "Überprüfung der Lokalisierbarkeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a>Überprüfung der Lokalisierbarkeit
Die Prüfung der Lokalisierbarkeit ist ein Zwischenschritt bei der Entwicklung einer weltweit einsetzbaren Anwendung. Er überprüft, ob eine globalisierte Anwendung ist bereit für die Lokalisierung bezeichnet jeglicher Code oder alle Aspekte der Benutzeroberfläche, die eine besondere Behandlung erfordern. Dieser Schritt wird auch sichergestellt, dass es sich bei der Lokalisierungsprozess Funktionsfehler nicht in die Anwendung integriert wird. Wenn Sie alle Probleme, die ausgelöst wird, indem Sie die Prüfung der Lokalisierbarkeit behandelt wurden, ist Ihre Anwendung für die Lokalisierung bereit. Wenn die Prüfung der Lokalisierbarkeit umfassend ist, sollten Sie keiner Quellcode während des Lokalisierungsprozesses zu ändern.  
  
 Die Prüfung der Lokalisierbarkeit umfasst die folgenden drei überprüft:  
  
-   [Werden die globalisierungsempfehlungen werden implementiert?](#global)  
  
-   [Werden kulturabhängigen Funktionen werden ordnungsgemäß behandelt?](#culture)  
  
-   [Haben Sie Ihre Anwendung mit internationalen Daten getestet?](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a>Implementieren von Globalisierungsempfehlungen  
 Wenn Sie entworfen und entwickelt von Ihrer Anwendung bei der Lokalisierung Bedenken haben und wenn Sie ausgeführt haben, werden die Empfehlungen im erläutert die [Globalisierung](../../../docs/standard/globalization-localization/globalization.md) Artikel, die Prüfung der Lokalisierbarkeit wird hauptsächlich Quality Assurance erfolgreich sein . Andernfalls, während dieser Phase sollten Sie lesen und implementieren Sie die Empfehlungen für [Globalisierung](../../../docs/standard/globalization-localization/globalization.md), und beheben Sie die Fehler im Quellcode, die Lokalisierung zu verhindern.  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a>Arbeiten mit kulturabhängigen Funktionen  
 .NET Framework bietet keine programmgesteuerte Unterstützung in verschiedenen Bereichen, die Kultur variieren. In den meisten Fällen müssen Sie zum Schreiben von benutzerdefiniertem Code, um Funktionsbereiche wie folgt behandeln:  
  
-   Adressen.  
  
-   Telefonnummern.  
  
-   Papierformate.  
  
-   Maßeinheiten für Längen, Gewichtungen, Bereich, Volume und Temperaturen verwendet. Obwohl .NET Framework keine integrierten Unterstützung für die Konvertierung zwischen Maßeinheiten anbieten, können Sie die <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> -Eigenschaft können Sie bestimmen, ob ein bestimmtes Land oder eine Region das metrische System verwendet, wie im folgenden Beispiel veranschaulicht.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a>Testen der Anwendung  
 Bevor Sie die Anwendung zu lokalisieren, sollten Sie es mit internationalen Daten in internationalen Versionen des Betriebssystems testen. Obwohl die meisten der Benutzeroberfläche zu diesem Zeitpunkt nicht lokalisiert werden, werden Sie z. B. die folgenden Probleme zu erkennen:  
  
-   Serialisierte Daten, die bei Betriebssystemversionen nicht korrekt deserialisiert werden.  
  
-   Numerische Daten, die nicht mit die Konventionen der aktuellen Kultur wiedergibt. Beispielsweise können Zahlen mit ungenaue Gruppentrennzeichen, Dezimaltrennzeichen oder Währungssymbole angezeigt werden.  
  
-   Datum und Uhrzeit-Daten, die nicht mit die Konventionen der aktuellen Kultur wiedergibt. Z. B. Zahlen, die den Monat und Tag darstellen, möglicherweise in der falschen Reihenfolge angezeigt, Datumstrennzeichen ist möglicherweise falsch oder die Zeitzoneninformationen ist möglicherweise falsch.  
  
-   Ressourcen, die nicht gefunden werden, weil Sie keine Standardkultur für die Anwendung identifiziert haben.  
  
-   Zeichenfolgen, die in einer ungewöhnlichen Reihenfolge für die spezifische Kultur angezeigt werden.  
  
-   Zeichenfolge vergleichen oder Vergleiche auf Gleichheit, die unerwartete Ergebnisse zurückgeben.  
  
 Wenn Sie haben die globalisierungsempfehlungen gefolgt, bei der Anwendungsentwicklung kulturabhängigen Funktionen ordnungsgemäß behandelt identifiziert und behandelt die Lokalisierungsprobleme, die während der Tests entstanden ist, können Sie mit dem nächsten Schritt fortfahren [Lokalisierung](../../../docs/standard/globalization-localization/localization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)  
 [Lokalisierung](../../../docs/standard/globalization-localization/localization.md)  
 [Globalisierung](../../../docs/standard/globalization-localization/globalization.md)  
 [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
