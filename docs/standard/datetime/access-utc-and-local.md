---
title: 'Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zone-Objekte'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7ddf7ba69d8bed84f62d329fd26794e2641d954
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571146"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zone-Objekte

Die <xref:System.TimeZoneInfo> Klasse enthält zwei Eigenschaften <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, die vordefinierte Zeitzonenobjekte Ihren Codezugriff erteilen. In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> koordinierte Weltzeit aufzurufende Eigenschaft.

2. Anstatt Zuweisen der <xref:System.TimeZoneInfo> Objekt von der Eigenschaft einer Objektvariablen zurückgegebene weiterhin Coordinated Universal Time, über den Zugriff auf die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft.

### <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft, um die Zeitzone des lokalen Systems zugreifen.

2. Anstatt Zuweisen der <xref:System.TimeZoneInfo> weiterhin über die lokale Zeitzone zugreifen, von der Eigenschaft an eine Objektvariable zurückgegebene Objekt der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft.

## <a name="example"></a>Beispiel

Der folgende code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaften zum Konvertieren einer Uhrzeit aus der USA und Kanadas Eastern Standard Time Zone sowie der Name der Zeitzone in der Konsole anzeigen.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Sollten Sie stets über die lokale Zeitzone zugreifen der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft anstatt der lokalen Zeit zone eine <xref:System.TimeZoneInfo> Object-Variablen. Ebenso sollten Sie stets Coordinated Universal Time, über zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft anstatt die UTC-zone auf eine <xref:System.TimeZoneInfo> Object-Variablen. Dies verhindert, dass die <xref:System.TimeZoneInfo> Objektvariable aus wird durch einen Aufruf für ungültig erklärt die <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[suchen die in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
