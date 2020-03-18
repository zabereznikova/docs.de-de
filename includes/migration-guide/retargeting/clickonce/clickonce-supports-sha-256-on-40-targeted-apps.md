---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804398"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce unterstützt SHA-256 auf Apps, die auf 4.0 ausgerichtet sind

|   |   |
|---|---|
|Details|Bisher war für ClickOnce-Apps mit einem mit SHA-256 signierten Zertifikat auch dann .NET Framework 4.5 oder höher erforderlich, wenn die App auf 4.0 ausgelegt war. Nun können ClickOnce-Apps, die auf .NET Framework 4.0 ausgelegt sind, auch dann in .NET Framework 4.0 ausgeführt werden, wenn sie mit SHA-256 signiert sind.|
|Vorschlag|Diese Änderung beseitigt diese Abhängigkeit und ermöglicht die Verwendung von SHA-256-Zertifikaten zum Signieren von ClickOnce-Apps, die auf .NET Framework 4 und frühere Versionen ausgerichtet sind.|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Neuzuweisung|
