---
ms.openlocfilehash: b23f06ec5b27fbd7976a4b62ba6105c607eaee39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236688"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Einige .NET-APIs führen zu erstmaligen (behandelten) EntryPointNotFoundExceptions

|   |   |
|---|---|
|Details|In .NET Framework 4.5 hat eine geringe Anzahl von .NET-Methoden damit begonnen, erstmalige <xref:System.EntryPointNotFoundException?displayProperty=name> auszulösen. Diese Ausnahmen wurden in .NET Framework behandelt, konnten aber die Testautomatisierung unterbrechen, die keine erstmaligen Ausnahmen erwartete. Dieselben APIs stören einige ApiVerifier-Szenarien, wenn „HighVersionLie“ aktiviert ist.|
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ kann die Testautomatisierung aktualisiert werden, damit keine Störung durch erstmalige <xref:System.EntryPointNotFoundException?displayProperty=name> erfolgt.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|
