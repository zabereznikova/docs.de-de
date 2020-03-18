---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802545"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme

|   |   |
|---|---|
|Details|WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=name> aus. Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden. Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.|
|Vorschlag|Upgrade auf .NET Framework 4.7|
|`Scope`|Edge|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Laufzeit|
