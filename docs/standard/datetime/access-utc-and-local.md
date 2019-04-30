---
title: 'Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
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
ms.openlocfilehash: c10c07c08a4e676cf3c84a5722814eaed85f74a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026607"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte

Die <xref:System.TimeZoneInfo> Klasse enthält zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, die Ihrem Code den Zugriff auf vordefinierte Zeitzonenobjekte ermöglichen. In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft, um die koordinierte Weltzeit zugreifen.

2. Anstatt die Zuweisung der <xref:System.TimeZoneInfo> Objekt einer Objektvariablen, von der Eigenschaft zurückgegebenen weiter, auf die koordinierte Weltzeit zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft.

### <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft, um die Zeitzone des lokalen Systems zugreifen.

2. Anstatt die Zuweisung der <xref:System.TimeZoneInfo> weiterhin die lokale Zeitzone zugreifen, von der Eigenschaft zurückgegebenen Objekts, einer Objektvariablen, die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft.

## <a name="example"></a>Beispiel

Der folgende code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaften, die zum Konvertieren einer Uhrzeit aus der US-amerikanischen und kanadischen Eastern Standard Time, sowie den Namen in der Konsole anzeigen.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Sie sollten immer die lokale Zeitzone zugreifen der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft anstatt der lokalen Zeit zone ein <xref:System.TimeZoneInfo> Objektvariable. Entsprechend sollten Sie immer koordinierte Weltzeit zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft anstatt die UTC-zone zu einer <xref:System.TimeZoneInfo> Objektvariable. Dies verhindert, dass die <xref:System.TimeZoneInfo> -Objektvariable wird durch einen Aufruf für ungültig erklärt die <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
