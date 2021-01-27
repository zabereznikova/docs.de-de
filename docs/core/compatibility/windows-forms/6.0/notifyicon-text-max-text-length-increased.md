---
title: 'Breaking Change: Maximale Textlänge für NotifyIcon.Text erhöht'
description: Erfahren Sie mehr über den Breaking Change in .NET 6.0, wo die maximale Textlänge für die Eigenschaft „NotifyIcon.Text“ zugenommen hat.
ms.date: 01/19/2021
ms.openlocfilehash: 0029556f3ec2795fb079575b329e7fbd187d486f
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98617976"
---
# <a name="notifyicontext-maximum-text-length-increased"></a>Maximale Textlänge für NotifyIcon.Text erhöht

Die maximal zulässige Textlänge für die <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType>-Eigenschaft wurde von 63 auf 127 Zeichen angehoben.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen betrug die maximal zulässige Textlänge für die <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType>-Eigenschaft 63 Zeichen. Ab .NET 6.0 beträgt die maximal zulässige Textlänge 127 Zeichen. In jeder Version wird eine <xref:System.ArgumentException>-Klasse ausgelöst, wenn Sie versuchen, einen Wert festzulegen, der den Grenzwert überschreitet.

## <a name="reason-for-change"></a>Grund für die Änderung

Die maximal zulässige Textlänge wurde in Übereinstimmung mit der [zugrunde liegenden Windows-API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080) erweitert. Die Windows-API wurde in Windows 2000 aktualisiert, aber aufgrund von Kompatibilitätsgründen wurde die Größenbeschränkung für diese Eigenschaft in .NET Framework nicht aktualisiert.

## <a name="version-introduced"></a>Eingeführt in Version

.NET Core 6.0 Preview 1

## <a name="recommended-action"></a>Empfohlene Maßnahme

Überprüfen Sie Ihren Code, und lockern Sie ggf. vorhandene Wächterbedingungen.

## <a name="affected-apis"></a>Betroffene APIs

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->
