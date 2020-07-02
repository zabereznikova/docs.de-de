---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622043"
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

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
