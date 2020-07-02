---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614474"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage löst für eintrittsinvariante Implementierungen von IMessageFilter.PreFilterMessage keine Ausnahmen mehr aus

#### <a name="details"></a>Details

Vor .NET Framework 4.6.1 verursachte das Aufrufen von <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> mit <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>, die <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> oder <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (bei gleichzeitigem Aufrufen von <xref:System.Windows.Forms.Application.DoEvents>) aufrief, eine <xref:System.IndexOutOfRangeException?displayProperty=fullName>.<p/>Seit der Verwendung von Anwendungen, die auf .NET Framework 4.6.1 abzielen, wird diese Ausnahme nicht mehr ausgelöst und es können eintrittsinvariante Filter verwendet werden, wie oben beschrieben.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> keine Ausnahmen mehr für das oben beschriebene eintrittsinvariante <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>-Verhalten auslöst. Dies wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Auf .NET Framework 4.6.1 ausgerichtete Apps können diese Änderung mithilfe der [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation)-Kompatibilitätsoption ablehnen (auf ältere Framework-Versionen ausgerichtete Apps können diese Option aktivieren).

| name          | Wert       |
|:--------------|:------------|
| Bereich         | Microsoft Edge        |
| Version       | 4.6.1       |
| Typ          | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>
