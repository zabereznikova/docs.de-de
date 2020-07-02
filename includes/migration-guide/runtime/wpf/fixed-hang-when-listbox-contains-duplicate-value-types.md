---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622015"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Problem mit ausbleibender Reaktion behoben, wenn „ListBox“ doppelte Werttypen enthält

#### <a name="details"></a>Details

Es wurde ein Problem behoben, das dazu führen konnte, dass ein virtualisierendes <xref:System.Windows.Controls.ItemsControl>-Steuerelement beim Scrollen nicht mehr reagiert, wenn die zugehörige Items-Auflistung Objekte mit doppelter Werttypisierung enthält.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.8|
|Typ|Laufzeit|
