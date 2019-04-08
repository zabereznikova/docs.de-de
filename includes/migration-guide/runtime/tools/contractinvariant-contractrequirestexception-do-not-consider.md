---
ms.openlocfilehash: 91e09e71a32bb6d410ff52a97a8d14384ee3a5f1
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58467080"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>„Contract.Invariant“ oder „Contract.Requires\<TException>“ erkennen „String.IsNullOrEmpty“ nicht als reinen Wert an

|   |   |
|---|---|
|Details|Für Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, gibt der Rewriter die Compilerwarnung CC1036 aus, wenn der Invariantvertrag für <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> oder der Vorbedingungsvertrag für <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> die Methode <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> aufruft: &quot;Aufruf der Methode <xref:System.String.IsNullOrWhiteSpace%2A?displayProperty=nameWithType> ohne [Pure] in der Methode erkannt.&quot; Dies ist eher eine Compilerwarnung als ein Compilerfehler.|
|Vorschlag|Dieses Verhalten wurde in [GitHub-Problem Nr. 339](https://github.com/Microsoft/CodeContracts/issues/339) behandelt. Um diese Warnung zu vermeiden, können Sie eine aktualisierte Version des Quellcodes für das Codevertragstool auf [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) herunterladen und kompilieren. Informationen zum Herunterladen befinden sich am unteren Rand der Seite.|
|Bereich|Gering|
|Version|4.6.1|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|

