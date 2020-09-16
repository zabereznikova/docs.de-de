---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 8a6f13da9bf05d87c45d86a09261d0c7245f5b00
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546907"
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

## <a name="remarks"></a>Hinweise

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.

Das- `<System.Windows.Forms.ApplicationConfigurationSection>` Element kann ein oder mehrere untergeordnete- [`<add>`](windows-forms-add-configuration-element.md) Elemente enthalten, von denen jedes eine bestimmte Konfigurationseinstellung definiert.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [Hohe dpi-Unterstützung in Windows Forms](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
