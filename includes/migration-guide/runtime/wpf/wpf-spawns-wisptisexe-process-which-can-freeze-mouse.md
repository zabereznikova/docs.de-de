---
ms.openlocfilehash: e0f72d19a884087b1f0f6ebd1b6baea75bc37af4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620484"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF erzeugt einen „wiptis.exe“-Prozess, der die Maus sperren kann

#### <a name="details"></a>Details

Mit Version 4.5.2 wurde ein Problem eingeführt, durch das <code>wisptis.exe</code> erzeugt wird. Hierdurch kann die Mauseingabe gesperrt werden.

#### <a name="suggestion"></a>Vorschlag

Eine Problembehebung steht in einem Service Release von .NET Framework 4.5.2 (Hotfixrollup 3026376) oder durch ein Upgrade auf .NET Framework 4.6 zur Verfügung.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5.2|
|Typ|Laufzeit|
