---
title: 'Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln'
ms.custom: 
ms.date: 04/10/2017
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 181d61de62ec9560b46732ad304b4934d4f55fa2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln

Die präzise Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht in einem bestimmten System verschiedenen Gründen vorhanden sein:

* Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

* Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.

* Die Zeitzone ist vorhanden, aber keine genaue Informationen zur zeitzonenanpassungen für einen bestimmten vergangene Zeitraum.

In diesen Fällen rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigt definieren. Die Überladungen dieser Methode können Sie um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen. Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit einer festen "oder" Gleitkomma Anpassungsregeln definieren. (Definitionen von Begriffen, finden Sie im Abschnitt "Zeitzone Terminology" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht an der Registrierung hinzugefügt. Stattdessen können sie nur über den Objektverweis zurückgegebenes aufgerufen werden der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methodenaufruf.

Dieses Thema veranschaulicht das Erstellen ohne Anpassungsregeln einer Zeitzone. Um eine Zeitzone zu erstellen, die die Anpassungsregeln Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>So erstellen eine Zeitzone ohne Anpassungsregeln

1. Anzeigename der Zeitzone zu definieren.

   Der Anzeigename folgt einem Standardformat in der die Zeitzone Offset von Coordinated Universal Time (UTC) in Klammern eingeschlossen und wird gefolgt von einer Zeichenfolge, die die Zeitzone, oder der Orte in der Zeitzone oder eine weitere mindestens eines der Cou identifiziert Osten oder Bereiche in der Zeitzone.

2. Der Name der Standardzeit der Zeitzone zu definieren. Diese Zeichenfolge wird in der Regel auch als Bezeichners der Zeitzone verwendet.

3. Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie des Zeitzonenbezeichners.

4. Instanziieren einer <xref:System.TimeSpan> Objekt, das die Zeitzone Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC haben einen positiven Offset. Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.

5. Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> Methode zum Instanziieren der neuen Zeitzone.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine benutzerdefinierte Zeitzone für Mawson, Antarktis, die keine Anpassungsregeln verfügt.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

Die zugewiesene Zeichenfolge die <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft resultiert aus einem Standardformat in dem Offset von UTC in die Zeitzone eine Beschreibung der Zeitzone folgt.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
