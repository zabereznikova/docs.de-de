---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606846"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute wird in WinMD-Szenarios sowohl als ObsoleteAttribute als auch als DeprecatedAttribute exportiert

#### <a name="details"></a>Details

Wenn Sie eine Windows-Metadatenbibliothek (WINMD-Datei) erstellen, wird das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> als <xref:System.ObsoleteAttribute?displayProperty=fullName> und als [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) exportiert.

#### <a name="suggestion"></a>Vorschlag

Durch die Neukompilierung von vorhandenem Quellcode, in dem das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> verwendet wird, können Warnungen generiert werden, wenn dieser Code von C++/CX oder JavaScript verarbeitet wird. Es wird davon abgeraten, sowohl <xref:System.ObsoleteAttribute?displayProperty=fullName> als auch [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) in Code in verwalteten Assemblys anzuwenden, da dies zu Buildwarnungen führen kann.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.5.1       |
| Typ    | Neuzuweisung |
