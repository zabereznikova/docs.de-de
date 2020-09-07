---
ms.openlocfilehash: 17fde81f9734966692c9f41d2213f8682dedea46
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496980"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant oder Contract.Requires\<TException> erkennen String.IsNullOrEmpty nicht als reinen Wert an

#### <a name="details"></a>Details

Für Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, gibt der Rewriter die Compilerwarnung CC1036 aus, wenn der Invariantvertrag für <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> oder der Vorbedingungsvertrag für <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> die Methode <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> aufruft: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method&quot; (Erkannter Aufruf von Methode 'System.String.IsNullOrWhteSpace(System.String)' ohne [Pure] in der Methode). Dies ist eher eine Compilerwarnung als ein Compilerfehler.

#### <a name="suggestion"></a>Vorschlag

Dieses Verhalten wurde in [GitHub-Problem Nr. 339](https://github.com/Microsoft/CodeContracts/issues/339) behandelt. Um diese Warnung zu vermeiden, können Sie eine aktualisierte Version des Quellcodes für das Codevertragstool auf [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) herunterladen und kompilieren. Informationen zum Herunterladen befinden sich am unteren Rand der Seite.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
