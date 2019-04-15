---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235770"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert

|   |   |
|---|---|
|Details|Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.|
|Vorschlag|Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten. Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
