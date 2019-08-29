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
ms.openlocfilehash: 510112c8b19ec002d1dcf918eb983b55dee68fd0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106668"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln

Die genauen Zeitzoneninformationen, die von einer Anwendung benötigt werden, sind möglicherweise aus verschiedenen Gründen nicht auf einem bestimmten System vorhanden:

- Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

- Daten über die Zeitzone wurden geändert oder aus der Registrierung entfernt.

- Die Zeitzone ist zwar vorhanden, verfügt jedoch nicht über genaue Informationen zu Zeit Zonen Anpassungen für einen bestimmten historischen Zeitraum.

In diesen Fällen können Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode zum Definieren der Zeitzone, die für Ihre Anwendung erforderlich ist, aufzurufen. Sie können die über Ladungen dieser Methode verwenden, um eine Zeitzone mit oder ohne Anpassungsregeln zu erstellen. Wenn die Zeitzone die Sommerzeit unterstützt, können Sie Anpassungen mit festgelegten oder Gleit Komma Anpassungsregeln definieren. (Informationen zu Definitionen dieser Begriffe finden Sie im Abschnitt "Zeit Zonen Terminologie" unter [Übersicht über](../../../docs/standard/datetime/time-zone-overview.md)die Zeitzone.)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen, die durch den <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Aufruf der-Methode erstellt wurden, werden nicht zur Registrierung hinzugefügt. Stattdessen kann nur über den Objekt Verweis darauf zugegriffen werden, der durch den <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methoden-Befehl zurückgegeben wird.

In diesem Thema wird gezeigt, wie Sie eine Zeitzone ohne Anpassungsregeln erstellen. Informationen zum Erstellen einer Zeitzone, die Anpassungsregeln für die Sommerzeit unter [stützt, finden Sie unter Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>So erstellen Sie eine Zeitzone ohne Anpassungsregeln

1. Hiermit wird der Anzeige Name der Zeitzone definiert.

   Der Anzeige Name folgt einem Recht standardmäßigen Format, in dem der Offset der Zeitzone von der koordinierten Weltzeit (UTC) in Klammern eingeschlossen wird, gefolgt von einer Zeichenfolge, die die Zeitzone, eine oder mehrere Städte in der Zeitzone oder eine oder mehrere der Orte (cou) identifiziert. ntries oder Regionen in der Zeitzone.

2. Hiermit wird der Name der Standardzeit der Zeitzone definiert. In der Regel wird diese Zeichenfolge auch als Bezeichner der Zeitzone verwendet.

3. Wenn Sie einen anderen Bezeichner als den Standardnamen der Zeitzone verwenden möchten, definieren Sie den Zeit Zonen Bezeichner.

4. Instanziieren Sie <xref:System.TimeSpan> ein-Objekt, das den Zeit Zonen Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC liegen, haben einen positiven Offset. Zeitzonen mit Zeiten, die älter sind als UTC, haben einen negativen Offset.

5. Ruft die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> -Methode auf, um die neue Zeitzone zu instanziieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine benutzerdefinierte Zeitzone für Mawson (Antarktis) definiert, die über keine Anpassungsregeln verfügt.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

Die Zeichenfolge, die <xref:System.TimeZoneInfo.DisplayName%2A> der-Eigenschaft zugewiesen ist, folgt einem Standardformat, bei dem der Offset der Zeitzone von UTC eine benutzerfreundliche Beschreibung der Zeitzone folgt.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Die folgenden Namespaces werden importiert:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
