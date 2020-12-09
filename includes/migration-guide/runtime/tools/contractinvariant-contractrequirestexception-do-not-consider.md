---
ms.openlocfilehash: 639cd13978cc33bd7c4524a17e92d566404bbaea
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477091"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant oder Contract.Requires\<TException> erkennen String.IsNullOrEmpty nicht als reinen Wert an

#### <a name="details"></a>Details

Für Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, gibt der Rewriter die Compilerwarnung CC1036 aus, wenn der Invariantvertrag für <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> oder der Vorbedingungsvertrag für <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> die Methode <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> aufruft: &quot;Erkannter Aufruf von Methode 'System.String.IsNullOrWhiteSpace(System.String)' ohne [Pure] in der Methode.&quot; Dies ist eher eine Compilerwarnung als ein Compilerfehler.

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
