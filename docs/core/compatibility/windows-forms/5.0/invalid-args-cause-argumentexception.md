---
title: 'Breaking Change: WinForms-Methoden lösen jetzt ArgumentException aus.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den einige Windows Forms-Methoden nun eine ArgumentException-Ausnahme für ungültige Argumente auslösen.
ms.date: 07/18/2020
ms.openlocfilehash: 46fe3f3b1208a5cd676e1b7546507bed36a850f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759564"
---
# <a name="winforms-methods-now-throw-argumentexception"></a>WinForms-Methoden lösen jetzt ArgumentException aus.

Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.

## <a name="change-description"></a>Änderungsbeschreibung

Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand. Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.

Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime. Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

## <a name="recommended-action"></a>Empfohlene Aktion

- Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.
- Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.

## <a name="affected-apis"></a>Betroffene APIs

In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:

| Methode | Parametername | Bedingung | Hinzugefügte Version |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>. | Vorschauversion 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | Das Argument ist `null`, <xref:System.String.Empty?displayProperty=nameWithType> oder Leerraum. | Preview 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | `InputLanguage` kann für die angegebene Kultur nicht abgerufen werden. | Preview 7 |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
