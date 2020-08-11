---
ms.openlocfilehash: 4fb1ffed97a5b7f906bed13a69f1e71563d11dae
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556173"
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

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Aktualisieren Sie jeden Code, der von diesen als serialisierbar markierten Typen abhängig ist.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- Keiner

<!--

#### Affected APIs

- Not detectable via API analysis

-->
