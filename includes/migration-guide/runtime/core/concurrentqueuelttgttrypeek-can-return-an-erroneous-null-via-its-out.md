---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622050"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben

#### <a name="details"></a>Details

In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.5.1 behoben. Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
