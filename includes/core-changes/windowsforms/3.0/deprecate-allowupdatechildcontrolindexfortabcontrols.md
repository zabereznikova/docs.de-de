---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556177"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt

Der Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` wird in Windows Forms unter .NET Framework 4.6 und höheren Versionen unterstützt. Er wird jedoch nicht unter .NET Core oder .NET 5.0 oder höher unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Wenn in .NET Framework 4.6 und höheren Versionen eine Registerkarte ausgewählt wird, wird die Steuerelementauflistung neu sortiert. Mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` kann eine Anwendung diese Neusortierung überspringen, sofern dieses Verhalten unerwünscht ist.

In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`-Switch nicht unterstützt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie den Switch. Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keiner

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
