---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856929"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Besseres KeyTips-Verhalten in WPF

|   |   |
|---|---|
|Details|Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht. Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend. Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.|
|Vorschlag|–|
|`Scope`|Edge|
|Version|4.7.2|
|Geben Sie Folgendes ein:|Laufzeit|
