---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621797"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme

#### <a name="details"></a>Details

WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=fullName> aus. Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden. Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.

#### <a name="suggestion"></a>Vorschlag

Upgrade auf .NET Framework 4.7

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.1|
|Typ|Laufzeit|
