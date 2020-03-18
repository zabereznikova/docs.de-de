---
ms.openlocfilehash: cbd599f7467c3b360bbe1c76a65abfdb840a1530
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803222"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF erzeugt einen „wiptis.exe“-Prozess, der die Maus sperren kann

|   |   |
|---|---|
|Details|Mit Version 4.5.2 wurde ein Problem eingeführt, durch das <code>wisptis.exe</code> erzeugt wird. Hierdurch kann die Mauseingabe gesperrt werden.|
|Vorschlag|Eine Problembehebung steht in einem Service Release von .NET Framework 4.5.2 (Hotfixrollup 3026376) oder durch ein Upgrade auf .NET Framework 4.6 zur Verfügung.|
|`Scope`|Major|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Laufzeit|
