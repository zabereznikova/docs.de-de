---
ms.openlocfilehash: 9f8a790718fbb9d685bb8959808338dc1766bf2c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021655"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus

Ab .NET Core 3.0 wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert in einem statischen <xref:System.Reflection.FieldAttributes.InitOnly>-Feld durch Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> festzulegen.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework und Versionen von .NET Core vor 3.0 konnten Sie den Wert eines statischen Felds, das nach der Initialisierung konstant ist ([schreibgeschützt in C#](~/docs/csharp/language-reference/keywords/readonly.md)), durch Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> festlegen. Allerdings führte das Festlegen eines solchen Felds auf diese Weise je nach Zielframework und Optimierungseinstellungen zu einem unvorhersehbaren Verhalten.

Ab . NET Core 3.0 wird beim Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A> für ein statisches <xref:System.Reflection.FieldAttributes.InitOnly>-Feld eine <xref:System.FieldAccessException?displayProperty=nameWithType>-Ausnahme ausgelöst.

> [!TIP]
> Ein <xref:System.Reflection.FieldAttributes.InitOnly>-Feld ist ein Feld, das nur zum Zeitpunkt seiner Deklaration oder im Konstruktor für die enthaltende Klasse festgelegt werden kann. Das heißt, dass es nach der Initialisierung konstant ist.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Initialisieren Sie statische <xref:System.Reflection.FieldAttributes.InitOnly>-Felder in einem statischen Konstruktor. Dies gilt sowohl für dynamische als auch für nicht dynamische Typen.

Alternativ können Sie das <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType>-Attribut aus dem Feld entfernen und dann <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>aufrufen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
