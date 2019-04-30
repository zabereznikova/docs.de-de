---
title: 'Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3ffc7b6f1f7baec7ce6beb5a50b706ff78bfa1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026548"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln

Die genaue Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht auf einem bestimmten System vorhanden, verschiedene Ursachen haben:

* Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

* Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.

* Die Zeitzone vorhanden ist, aber keine genaue Informationen zur zeitzonenanpassungen für einen bestimmten Zeitraum für vergangene.

Sie können in diesen Fällen Aufrufen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigten definieren. Sie können die Überladungen dieser Methode verwenden, um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen. Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit entweder feste "oder" Gleitkomma Anpassungsregeln definieren. (Für die Definitionen dieser Begriffe finden Sie im Abschnitt "Zeitzonenterminologie" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht in der Registrierung hinzugefügt. Stattdessen können sie nur über das vom Objektverweis zugegriffen werden die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methodenaufruf.

In diesem Thema zeigt, wie eine Zeitzone ohne Anpassungsregeln erstellt wird. Um eine Zeitzone zu erstellen, die Anpassungsregeln für die Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Erstellen Sie eine Zeitzone ohne Anpassungsregeln

1. Anzeigename der Zeitzone zu definieren.

   Der Anzeigename folgt ein Standardformat in der der Standardzeit der Zeitzone Offset von Coordinated Universal Time (UTC) wird in Klammern eingeschlossen werden soll, und folgt eine Zeichenfolge, die Zeitzone oder der Städte in der Zeitzone oder eine weitere mindestens die Cou identifiziert Osten oder Regionen, in der Zeitzone.

2. Der Name der Standardzeit der Zeitzone zu definieren. Diese Zeichenfolge wird in der Regel auch als Bezeichner für die Zeitzone verwendet.

3. Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie den Zeitzonenbezeichner.

4. Instanziieren einer <xref:System.TimeSpan> -Objekt, das die Zeitzone Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC weisen einen positiven Offset. Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.

5. Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> Methode, um die neue Zeitzone zu instanziieren.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine benutzerdefinierte Zeitzone für Mawson, Antarktis, die keine Anpassungsregeln verfügt.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

Die zugewiesene Zeichenfolge die <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft hat ein Standardformat, die in der Offset von der Standardzeit der Zeitzone von UTC eine Beschreibung der Zeitzone folgt.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
