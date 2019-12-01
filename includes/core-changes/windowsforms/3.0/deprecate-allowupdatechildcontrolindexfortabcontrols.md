---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643886"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Kompatibilitätsswitch „Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls“ wird nicht unterstützt

Der Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` wird in Windows Forms unter .NET Framework 4.6 und höheren Versionen unterstützt. In Windows Forms ab .NET Core 3.0 gibt es diese Unterstützung jedoch nicht mehr.

#### <a name="change-description"></a>Änderungsbeschreibung

Wenn in .NET Framework 4.6 und höheren Versionen eine Registerkarte ausgewählt wird, wird die Steuerelementauflistung neu sortiert. Mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` kann eine Anwendung diese Neusortierung überspringen, sofern dieses Verhalten unerwünscht ist.

In .NET Core wird der Switch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keine

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
