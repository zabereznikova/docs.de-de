---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4de61ae3cb5eb8a3fc226881e2b7f842030dfddf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151831"
---
# <a name="windows-forms-configuration-section"></a>Konfigurationsabschnitt für Windows Forms
Konfigurationseinstellungen für Windows Forms ermöglichen einer Windows Forms-App das Speichern und Abrufen von Informationen über benutzerdefinierte Anwendungseinstellungen wie z.B. Unterstützung mehrerer Monitore, Unterstützung für hohe DPI-Werte sowie weitere vorab definierte Konfigurationseinstellungen.

Windows Forms-Anwendungskonfigurationseinstellungen werden im `System.Windows.Forms.ApplicationConfigurationSection`-Element der Anwendungskonfigurationsdatei gespeichert.

## <a name="syntax"></a>Syntax

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Element  |BESCHREIBUNG |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu. |

### <a name="parent-elements"></a>Übergeordnete Elemente

Element  |BESCHREIBUNG |
---------|---------|
[\<configuration>](../configuration-element.md) | Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="remarks"></a>Bemerkungen

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.

Das- `<System.Windows.Forms.ApplicationConfigurationSection>` Element kann ein oder mehrere untergeordnete- [`<add>`](windows-forms-add-configuration-element.md) Elemente enthalten, von denen jedes eine bestimmte Konfigurationseinstellung definiert.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [Hohe dpi-Unterstützung in Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
