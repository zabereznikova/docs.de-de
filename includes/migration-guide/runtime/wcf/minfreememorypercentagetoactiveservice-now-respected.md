---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620363"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService wird jetzt eingehalten

#### <a name="details"></a>Details

Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Sie dient dazu, <xref:System.OutOfMemoryException?displayProperty=fullName>-Ausnahmen zu verhindern. In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung. In .NET Framework 4.5.1 wird die Einstellung beobachtet.

#### <a name="suggestion"></a>Vorschlag

Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5.1|
|Typ|Laufzeit|
