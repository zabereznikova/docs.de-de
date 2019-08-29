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
ms.openlocfilehash: 8aa19118ce0837b9ce0eb523f3e086fcbcecb9e8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106562"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte

Die <xref:System.TimeZoneInfo> -Klasse stellt zwei Eigenschaften <xref:System.TimeZoneInfo.Utc%2A> , <xref:System.TimeZoneInfo.Local%2A>und, bereit, die Ihrem Code den Zugriff auf vordefinierte Zeit Zonen Objekte ermöglichen. In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden Sie `static` die`Shared` -Eigenschaft ( <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> in Visual Basic) für den Zugriff auf die koordinierte Weltzeit.

2. Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin auf die koordinierte Weltzeit über die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> -Eigenschaft zu.

### <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden Sie `static` die`Shared` -Eigenschaft ( <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> in Visual Basic) für den Zugriff auf die lokale Systemzeitzone.

2. Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft auf die lokale Zeitzone zu.

## <a name="example"></a>Beispiel

Der folgende Code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> - <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft und die-Eigenschaft, um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren, sowie den Namen der Zeitzone auf der Konsole anzuzeigen.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Sie sollten stets über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft auf die lokale Zeitzone zugreifen, anstatt die lokale Zeitzone einer <xref:System.TimeZoneInfo> -Objektvariablen zuzuweisen. Ebenso sollten Sie immer über die-Eigenschaft auf die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> koordinierte Weltzeit zugreifen, anstatt die UTC-Zone einer <xref:System.TimeZoneInfo> -Objektvariablen zuzuweisen. Dadurch wird verhindert <xref:System.TimeZoneInfo> , dass die Objekt Variable durch einen Aufrufder <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> -Methode ungültig gemacht wird.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace, der mit der `using` -Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
