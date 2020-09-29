---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738818"
---
### <a name="parameter-names-changed-in-rc1"></a>Parameternamen in RC1 geändert

Einige Parameternamen für Referenzassemblys wurden so geändert, dass sie mit den Parameternamen in den Implementierungsassemblys übereinstimmen.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET 5.0 Preview- und RC-Versionen unterscheiden sich einige Parameternamen in [Referenzassemblys](../../../../docs/standard/assembly/reference-assemblies.md) von den entsprechenden Parametern in der Implementierungsassembly. Dies kann Probleme bei der Verwendung von benannten Argumenten und Reflexion verursachen.

In .NET 5.0 RC2 wurden diese nicht übereinstimmenden Parameternamen in den Referenzassemblys so aktualisiert, dass sie den entsprechenden Parameternamen in den Implementierungsassemblys exakt entsprechen.

In der folgenden Tabelle sind die APIs und Parameternamen aufgeführt, die sich geändert haben.

| API | Alter Parametername | Neuer Parametername |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Parameternamen wurden aus Gründen der Konsistenz und zum Vermeiden von Fehlern bei der Verwendung von benannten Argumenten und Reflexion geändert.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn aufgrund der Änderung eines Parameternamens ein Compilerfehler auftritt, aktualisieren Sie den Parameternamen entsprechend.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
