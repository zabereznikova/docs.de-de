---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236133"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Besseres KeyTips-Verhalten in WPF

|   |   |
|---|---|
|Details|Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht. Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend. Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.|
|Vorschlag|Nicht zutreffend|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|
