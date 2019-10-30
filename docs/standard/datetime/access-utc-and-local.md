---
title: 'Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeit Zonen Objekte'
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
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132605"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeit Zonen Objekte

Die <xref:System.TimeZoneInfo>-Klasse bietet zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, die Ihrem Code den Zugriff auf vordefinierte Zeit Zonen Objekte ermöglichen. In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden Sie die `static`-Eigenschaft (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>, um auf die koordinierte Weltzeit zuzugreifen.

2. Anstatt das <xref:System.TimeZoneInfo> Objekt, das von der-Eigenschaft zurückgegeben wird, einer Objektvariablen zuzuweisen, greifen Sie weiterhin auf die koordinierte Weltzeit über die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>-Eigenschaft zu.

### <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden Sie die `static`-Eigenschaft (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>, um auf die lokale Systemzeitzone zuzugreifen.

2. Anstatt das <xref:System.TimeZoneInfo> Objekt, das von der-Eigenschaft zurückgegeben wird, einer Objektvariablen zuzuweisen, greifen Sie weiterhin über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>-Eigenschaft auf die lokale Zeitzone zu.

## <a name="example"></a>Beispiel

Im folgenden Code werden die Eigenschaften <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> verwendet, um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren sowie den Namen der Zeitzone auf der Konsole anzuzeigen.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Sie sollten stets über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>-Eigenschaft auf die lokale Zeitzone zugreifen, anstatt die lokale Zeitzone einer <xref:System.TimeZoneInfo>-Objektvariablen zuzuweisen. Ebenso sollten Sie immer über die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>-Eigenschaft auf die koordinierte Weltzeit zugreifen, anstatt die UTC-Zone einer <xref:System.TimeZoneInfo>-Objektvariablen zuzuweisen. Dadurch wird verhindert, dass die <xref:System.TimeZoneInfo> Objekt Variable durch einen aufzurufenden <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode ungültig wird.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- , Dass der <xref:System> Namespace mit der `using`-Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
