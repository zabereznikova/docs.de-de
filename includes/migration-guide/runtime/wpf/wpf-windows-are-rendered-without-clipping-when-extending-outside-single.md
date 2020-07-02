---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621354"
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
