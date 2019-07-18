---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235639"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService wird jetzt eingehalten

|   |   |
|---|---|
|Details|Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Sie dient dazu, <xref:System.OutOfMemoryException?displayProperty=name>-Ausnahmen zu verhindern. In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung. In .NET Framework 4.5.1 wird die Einstellung beobachtet.|
|Vorschlag|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|
