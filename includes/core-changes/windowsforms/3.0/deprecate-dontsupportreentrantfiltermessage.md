---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643892"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Kompatibilitätsswitch „Switch.System.Windows.Forms.DontSupportReentrantFilterMessage“ wird nicht unterstützt

Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.6.1 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` mögliche <xref:System.IndexOutOfRangeException>-Ausnahmen behandelt, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Nachricht mit einer benutzerdefinierten <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung aufgerufen wird. Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

In .NET Core wird der Switch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
