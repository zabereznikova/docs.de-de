---
title: Konfigurationsabschnitt für Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbb2c4157ba702182056c98c959a60569e8c3d1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786411"
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

Element  |Beschreibung |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | Fügt einen Konfigurationseinstellungsschlüssel mit einem angegebenen Wert hinzu. |

### <a name="parent-elements"></a>Übergeordnete Elemente

Element  |Beschreibung |
---------|---------|
[\<configuration>](../configuration-element.md) | Das Stammelement in jeder von der Common Language Runtime und Windows Forms-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="remarks"></a>Hinweise

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden. 

Das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element kann ein oder mehrere [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)-Elemente enthalten, die jeweils eine bestimmte Konfigurationseinstellung definieren.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
