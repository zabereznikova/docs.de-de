---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236696"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue\<T>.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben

|   |   |
|---|---|
|Details|In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.1 behoben. Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
