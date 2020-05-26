---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702476"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>WinForms-Methoden lösen jetzt ArgumentException aus.

Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand. Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.

Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime. Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.

In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:

| Methode | Parametername | Bedingung | Hinzugefügte Version |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>. | 5.0 Preview 1 |

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0 Preview 1

#### <a name="recommended-action"></a>Empfohlene Aktion

- Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.
- Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
