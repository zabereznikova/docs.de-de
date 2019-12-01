---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643850"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a>SerializableAttribute aus einigen Windows Forms-Typen entfernt

<xref:System.SerializableAttribute> wurde aus einigen Windows Forms-Klassen ohne bekannte Szenarios für binäre Serialisierung entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

Die folgenden Typen enthalten in .NET Framework das Attribut <xref:System.SerializableAttribute>, das in .NET Core entfernt wurde:

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

In der Vergangenheit bereitete dieser Serialisierungsmechanismus schwerwiegende Wartungs- und Sicherheitsprobleme. Die Beibehaltung von `SerializableAttribute` für Typen bedeutet, dass diese Typen auf Serialisierungsänderungen zwischen Versionen und auf potenzielle Serialisierungsänderungen zwischen Frameworks geprüft werden müssen. Dies erschwert die Weiterentwicklung dieser Typen und verteuert die Beibehaltung. Da es für diese Typen keine bekannten Serialisierungsszenarios gibt, sind die Auswirkungen minimal, wenn das Attribut entfernt wird.

Weitere Informationen finden Sie unter [Binäre Serialisierung](~/docs/standard/serialization/binary-serialization.md).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 9

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie jeden Code, der von diesen als serialisierbar markierten Typen abhängig ist.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keine

<!--

### Affected APIs

- Not detectable via API analysis

-->
