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
ms.openlocfilehash: ebb07800b2a35f4faf312dc55b8c5679079b4b68
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291408"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte

Die <xref:System.TimeZoneInfo> -Klasse stellt zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und, bereit, <xref:System.TimeZoneInfo.Local%2A> die Ihrem Code den Zugriff auf vordefinierte Zeit Zonen Objekte ermöglichen. In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden Sie die- `static` `Shared` Eigenschaft (in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> für den Zugriff auf die koordinierte Weltzeit.

2. Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin auf die koordinierte Weltzeit über die- <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft zu.

### <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden Sie die- `static` `Shared` Eigenschaft (in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> für den Zugriff auf die lokale Systemzeitzone.

2. Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin über die-Eigenschaft auf die lokale Zeitzone zu <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> .

## <a name="example"></a>Beispiel

Der folgende Code verwendet die-Eigenschaft <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> -Eigenschaft, um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren, sowie den Namen der Zeitzone auf der Konsole anzuzeigen.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

Sie sollten stets über die-Eigenschaft auf die lokale Zeitzone zugreifen <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> , anstatt die lokale Zeitzone einer- <xref:System.TimeZoneInfo> Objektvariablen zuzuweisen. Ebenso sollten Sie immer über die-Eigenschaft auf die koordinierte Weltzeit zugreifen, <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> anstatt die UTC-Zone einer- <xref:System.TimeZoneInfo> Objektvariablen zuzuweisen. Dadurch wird verhindert, <xref:System.TimeZoneInfo> dass die Objekt Variable durch einen Aufrufder-Methode ungültig gemacht wird <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> .

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)
- [Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md)
