---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556174"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt

Der Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework ist es mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` möglich, dass eine Anwendung die Prüfung von visuellen Elementen abstellt, die in einer numerischen Form bereitgestellt werden.

In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.EnableVisualStyleValidation`-Switch nicht unterstützt.

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
