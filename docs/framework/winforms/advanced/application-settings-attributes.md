---
title: Attribute für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: 9ed549cb1e10b22c4fa34d984133a6be11dfab44
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525111"
---
# <a name="application-settings-attributes"></a>Attribute für Anwendungseinstellungen
Architektur der Anwendungseinstellungen enthält viele Attribute, die entweder auf die Anwendungen Einstellungen-Wrapperklasse oder ihre individuellen Eigenschaften angewendet werden können. Diese Attribute werden zur Laufzeit durch die Einstellungen Anwendungsstruktur, häufig speziell der Einstellungsanbieter, untersucht, um anzupassen, die funktioniert auf die angegebenen Anforderungen von den benutzerdefinierten Wrapper.  
  
 Die folgende Tabelle enthält die Attribute, die auf die Wrapperklasse für Anwendungseinstellungen, einzelne Eigenschaften dieser Klasse oder beides angewendet werden können. Per definitionem nur ein einziges Bereichsattribut –**UserScopedSettingAttribute** oder **ApplicationScopedSettingAttribute**– muss auf jede Eigenschaft angewendet werden.  
  
> [!NOTE]
>  Ein benutzerdefinierten Einstellungsanbieter, abgeleitet aus den <xref:System.Configuration.SettingsProvider> Klasse, muss nur die folgenden drei Attribute erkennen: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, und **DefaultSettingValueAttribute**.  
  
|Attribut|Ziel|Beschreibung|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Beides|Gibt den kurzen Namen des Einstellungsanbieters für Persistenz verwendet.<br /><br /> Wenn dieses Attribut nicht angegeben ist, der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>, wird angenommen.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als eine benutzerspezifische anwendungseinstellung an.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als im Gültigkeitsbereich der Anwendung anwendungseinstellung an.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Eigenschaft|Gibt eine Zeichenfolge, die in den Wert fest codierter Standardwert für diese Eigenschaft vom Anbieter deserialisiert werden kann.<br /><br /> Die <xref:System.Configuration.LocalFileSettingsProvider> dieses Attribut ist nicht erforderlich und durch einen beliebigen Wert überschrieben werden, bereitgestellt von diesem Attribut liegt ein Wert bereits erhalten bleibt.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Eigenschaft|Enthält den beschreibenden Text für eine einzelne Einstellung, die in erster Linie von der Laufzeit und Entwurfszeit-Tools verwendet.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Klasse|Stellt einen expliziten Namen für eine Gruppe "Einstellungen". Wenn dieses Attribut fehlt, ist <xref:System.Configuration.ApplicationSettingsBase> der Wrapper-Klassenname verwendet.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Klasse|Enthält den beschreibenden Text für eine Gruppe "Einstellungen" in erster Linie von der Laufzeit und Entwurfszeit-Tools verwendet.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Beides|Gibt NULL oder mehr Verwaltbarkeit-Dienste, die der Gruppe "Einstellungen" oder die Eigenschaft bereitgestellt werden soll. Die verfügbaren Dienste gelten die <xref:System.Configuration.SettingsManageability> Enumeration.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Eigenschaft|Gibt an, dass eine Einstellung auf eine spezielle, vordefinierte Kategorie, z. B. eine Verbindungszeichenfolge gehört, die spezielle Verarbeitung durch den Einstellungsanbieter vorschlägt. Die vordefinierten Kategorien für dieses Attribut definieren, indem die <xref:System.Configuration.SpecialSetting> Enumeration.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Beides|Gibt einen bevorzugten Serialisierungsmechanismus für eine Gruppe oder Eigenschaft an. Die verfügbaren Serialisierungsmechanismen werden definiert, indem die <xref:System.Configuration.SettingsSerializeAs> Enumeration.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Eigenschaft|Gibt an, dass ein Einstellungsanbieter alle Upgrade Anwendungsfunktionalität für die markierte Eigenschaft deaktivieren soll.|  
  
 *Klasse* gibt an, dass das Attribut nur auf eine Wrapperklasse für Anwendungseinstellungen angewendet werden kann. *Eigenschaft* gibt an, dass das Attribut nur Einstellungseigenschaften angewendet werden kann. *Beide* gibt an, dass das Attribut auf beiden Ebenen angewendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Vorgehensweise: Erstellen von Anwendungseinstellungen](https://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
