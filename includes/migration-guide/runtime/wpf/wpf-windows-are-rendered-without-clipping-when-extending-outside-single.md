---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497335"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>WPF-Fenster werden ohne Clipping gerendert, wenn diese die Größe eines einzelnen Monitors überschreiten

#### <a name="details"></a>Details

In .NET Framework 4.6, das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt. Dies unterscheidet sich von früheren Versionen von .NET Framework, bei denen WPF-Fenster beschnitten werden, die eine einzelne Anzeige überschreiten.

#### <a name="suggestion"></a>Vorschlag

Dieses Verhalten (ob ein Clipping angewendet wird oder nicht) kann explizit festgelegt werden, indem Sie das <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code>-Element von <code>&lt;appSettings&gt;</code> in der Konfigurationsdatei einer Anwendung verwenden oder indem Sie die <code>EnableMultiMonitorDisplayClipping</code>-Eigenschaft beim Starten der App festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
