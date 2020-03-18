---
ms.openlocfilehash: 8a1e2ca0790cb62e3c2c879f2ba0bb169ef07d77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804335"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage löst für eintrittsinvariante Implementierungen von IMessageFilter.PreFilterMessage keine Ausnahmen mehr aus

|   |   |
|---|---|
|Details|Vor .NET Framework 4.6.1 verursachte das Aufrufen von <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> mit <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>, die <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> oder <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> (bei gleichzeitigem Aufrufen von <xref:System.Windows.Forms.Application.DoEvents>) aufrief, eine <xref:System.IndexOutOfRangeException?displayProperty=name>.<p/>Seit der Verwendung von Anwendungen, die auf .NET Framework 4.6.1 abzielen, wird diese Ausnahme nicht mehr ausgelöst und es können eintrittsinvariante Filter verwendet werden, wie oben beschrieben.|
|Vorschlag|Beachten Sie, dass <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> keine Ausnahmen mehr für das oben beschriebene eintrittsinvariante <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>-Verhalten auslöst. Dies wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Auf .NET Framework 4.6.1 ausgerichtete Apps können diese Änderung mithilfe der [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation)-Kompatibilitätsoption ablehnen (auf ältere Framework-Versionen ausgerichtete Apps können diese Option aktivieren).|
|`Scope`|Edge|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType></li></ul>|
