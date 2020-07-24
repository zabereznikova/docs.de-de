---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309145"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>WinForms-Methoden lösen jetzt ArgumentException aus.

Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand. Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.

Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime. Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

#### <a name="recommended-action"></a>Empfohlene Aktion

- Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.
- Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:

| Methode | Parametername | Bedingung | Hinzugefügte Version |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>. | Vorschauversion 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | Das Argument ist `null`, <xref:System.String.Empty?displayProperty=nameWithType> oder Leerraum. | Preview 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | `InputLanguage` kann für die angegebene Kultur nicht abgerufen werden. | Preview 7 |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->
