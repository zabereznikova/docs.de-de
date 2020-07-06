---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616114"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute wird in WinMD-Szenarios sowohl als ObsoleteAttribute als auch als DeprecatedAttribute exportiert

#### <a name="details"></a>Details

Wenn Sie eine Windows-Metadatenbibliothek (WINMD-Datei) erstellen, wird das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> als <xref:System.ObsoleteAttribute?displayProperty=fullName> und als [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) exportiert.

#### <a name="suggestion"></a>Vorschlag

Durch die Neukompilierung von vorhandenem Quellcode, in dem das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> verwendet wird, können Warnungen generiert werden, wenn dieser Code von C++/CX oder JavaScript verarbeitet wird. Es wird davon abgeraten, sowohl <xref:System.ObsoleteAttribute?displayProperty=fullName> als auch [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) in Code in verwalteten Assemblys anzuwenden, da dies zu Buildwarnungen führen kann.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.5.1       |
| Typ    | Neuzuweisung |
