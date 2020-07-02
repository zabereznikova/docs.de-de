---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620402"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert

#### <a name="details"></a>Details

Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.

#### <a name="suggestion"></a>Vorschlag

Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten. Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|
