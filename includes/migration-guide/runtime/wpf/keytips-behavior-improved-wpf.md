---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621270"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Besseres KeyTips-Verhalten in WPF

#### <a name="details"></a>Details

Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht. Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend. Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.

#### <a name="suggestion"></a>Vorschlag

Nicht zutreffend

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|
