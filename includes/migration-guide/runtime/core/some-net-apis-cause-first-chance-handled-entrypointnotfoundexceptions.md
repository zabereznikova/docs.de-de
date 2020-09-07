---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497868"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Einige .NET-APIs führen zu erstmaligen (behandelten) EntryPointNotFoundExceptions

#### <a name="details"></a>Details

In .NET Framework 4.5 hat eine geringe Anzahl von .NET-Methoden damit begonnen, erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> auszulösen. Diese Ausnahmen wurden in .NET Framework behandelt, konnten aber die Testautomatisierung unterbrechen, die keine erstmaligen Ausnahmen erwartete. Dieselben APIs stören einige ApiVerifier-Szenarien, wenn „HighVersionLie“ aktiviert ist.

#### <a name="suggestion"></a>Vorschlag

Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ kann die Testautomatisierung aktualisiert werden, damit keine Störung durch erstmalige <xref:System.EntryPointNotFoundException?displayProperty=fullName> erfolgt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->
