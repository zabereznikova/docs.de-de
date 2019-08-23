---
title: Attribute für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: b38ed931cab3a333a56dd027d5843b1c8f00dcb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916684"
---
# <a name="application-settings-attributes"></a>Attribute für Anwendungseinstellungen
Die Architektur der Anwendungseinstellungen bietet viele Attribute, die entweder auf die Wrapper Klasse für Anwendungseinstellungen oder die jeweiligen Eigenschaften angewendet werden können. Diese Attribute werden zur Laufzeit von der Infrastruktur für Anwendungseinstellungen untersucht, häufig insbesondere vom Einstellungs Anbieter, um die Funktionsweise an die für den benutzerdefinierten Wrapper angewenden Anforderungen anzupassen.  
  
 In der folgenden Tabelle werden die Attribute aufgelistet, die auf die Wrapper Klasse für Anwendungseinstellungen, die einzelnen Eigenschaften dieser Klasse oder beides angewendet werden können. Definitionsgemäß muss nur ein einzelnes Bereichs Attribut –**UserScopedSettingAttribute** oder **ApplicationScopedSettingAttribute**– auf jede Settings-Eigenschaft angewendet werden.  
  
> [!NOTE]
> Ein von der <xref:System.Configuration.SettingsProvider> -Klasse abgeleiteter benutzerdefinierter Einstellungs Anbieter ist nur erforderlich, um die folgenden drei Attribute zu erkennen: " **ApplicationScopedSettingAttribute**", " **UserScopedSettingAttribute**" und " **DefaultSettingValueAttribute**".  
  
|Attribut|Ziel|Beschreibung|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Beides|Gibt den Kurznamen des Einstellungs Anbieters an, der für Persistenz verwendet werden soll.<br /><br /> Wenn dieses Attribut nicht angegeben wird, wird der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>,, angenommen.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als benutzerspezifische Anwendungs Einstellung.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als anwendungsspezifische Anwendungs Einstellung.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Eigenschaft|Gibt eine Zeichenfolge an, die vom Anbieter in den hart codierten Standardwert für diese Eigenschaft deserialisiert werden kann.<br /><br /> Erfordert <xref:System.Configuration.LocalFileSettingsProvider> dieses Attribut nicht und überschreibt alle Werte, die von diesem Attribut bereitgestellt werden, wenn bereits ein Wert persistent ist.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Eigenschaft|Stellt den beschreibenden Test für eine individuelle Einstellung bereit, die in erster Linie von Lauf Zeit-und Entwurfszeit Tools verwendet wird.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Klasse|Stellt einen expliziten Namen für eine Einstellungs Gruppe bereit. Wenn dieses Attribut fehlt, <xref:System.Configuration.ApplicationSettingsBase> wird der Wrapper Klassenname verwendet.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Klasse|Stellt den beschreibenden Test für eine Einstellungs Gruppe bereit, die in erster Linie von Lauf Zeit-und Entwurfszeit Tools verwendet wird.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Beides|Gibt NULL oder mehr verwaltbarkeitsdienste an, die für die Einstellungs Gruppe oder-Eigenschaft bereitgestellt werden sollen. Die verfügbaren Dienste werden von der <xref:System.Configuration.SettingsManageability> -Enumeration beschrieben.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Eigenschaft|Gibt an, dass eine Einstellung zu einer speziellen, vordefinierten Kategorie gehört, z. b. eine Verbindungs Zeichenfolge, die eine besondere Verarbeitung durch den Einstellungs Anbieter vorschlägt. Die vordefinierten Kategorien für dieses Attribut werden durch die <xref:System.Configuration.SpecialSetting> -Enumeration definiert.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Beides|Gibt einen bevorzugten Serialisierungsmechanismus für eine Einstellungs Gruppe oder Eigenschaft an. Die verfügbaren Serialisierungsmechanismen werden von <xref:System.Configuration.SettingsSerializeAs> der-Enumeration definiert.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Eigenschaft|Gibt an, dass ein Einstellungs Anbieter alle anwendungsupgradefunktionen für die markierte Eigenschaft deaktivieren soll.|  
  
 *Klasse* gibt an, dass das Attribut nur auf eine Wrapper Klasse für Anwendungseinstellungen angewendet werden kann. *Eigenschaft* gibt an, dass das Attribut nur Einstellungs Eigenschaften angewendet werden kann. *Beide* gibt an, dass das Attribut auf jeder Ebene angewendet werden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Architektur der Anwendungseinstellungen](application-settings-architecture.md)
- [Vorgehensweise: Erstellen von Anwendungseinstellungen](how-to-create-application-settings.md)
