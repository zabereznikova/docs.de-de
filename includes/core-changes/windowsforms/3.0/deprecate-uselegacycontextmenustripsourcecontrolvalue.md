---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643904"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Kompatibilitätsswitch „Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue“ wird nicht unterstützt

Der mit .NET Framework 4.7.2 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Framework 4.7.2 kann der Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` das neue Verhalten der <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft abstellen, mit dem nun ein Verweis an die Quellcodeverwaltung zurückgegeben wird. Mit dem früheren Verhalten der Eigenschaft wurde `null` zurückgegeben. Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core wird der Switch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
