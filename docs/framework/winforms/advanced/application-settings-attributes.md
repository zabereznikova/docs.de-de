---
title: "Attribute für Anwendungseinstellungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1879ac6704619092c4c0d9cd6fab0356ea07a13d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="application-settings-attributes"></a>Attribute für Anwendungseinstellungen
Die Anwendungseinstellungen-Architektur bietet viele Attribute, die für die Wrapperklasse für Applikationen-Einstellungen oder der einzelnen Eigenschaften angewendet werden können. Diese Attribute werden zur Laufzeit von der Anwendung Einstellungen Infrastruktur häufig speziell der Einstellungsanbieter untersucht, um seine ordnungsgemäße Ausführung benutzerdefinierte Wrapper genannten Anforderungen anzupassen.  
  
 Die folgende Tabelle enthält die Attribute, die auf die Wrapperklasse für Anwendungseinstellungen, einzelne Eigenschaften dieser Klasse oder beides angewendet werden können. Laut Definition sind nur ein einziges Bereichsattribut –**UserScopedSettingAttribute** oder **ApplicationScopedSettingAttribute**– muss für jede Eigenschaft angewendet werden.  
  
> [!NOTE]
>  Ein benutzerdefinierten Einstellungsanbieter abgeleitet wurde. die <xref:System.Configuration.SettingsProvider> Klasse, ist nur erforderlich, erkennt die folgenden drei Attribute: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, und **DefaultSettingValueAttribute**.  
  
|Attribut|Ziel|Beschreibung|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Beides|Gibt den kurzen Namen des Anbieters Einstellungen an, für den permanenten Speicher verwendet.<br /><br /> Wenn dieses Attribut nicht angegeben ist, den Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>, wird angenommen.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als eine benutzerspezifische anwendungseinstellung an.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als im Gültigkeitsbereich der Anwendung anwendungseinstellung an.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Eigenschaft|Gibt eine Zeichenfolge, die in der fest programmierte Standardwert für diese Eigenschaft vom Anbieter deserialisiert werden kann.<br /><br /> Die <xref:System.Configuration.LocalFileSettingsProvider> erfordert dieses Attribut keine und ausnahmslos überschrieben werden, sofern durch dieses Attribut ist ein Wert bereits beibehalten.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Eigenschaft|Enthält den beschreibenden Text für eine einzelne Einstellung, die hauptsächlich von Tools zur Laufzeit und Entwurfszeit verwendet.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Klasse|Stellt einen expliziten Namen für eine Einstellungsgruppe. Wenn dieses Attribut fehlt, <xref:System.Configuration.ApplicationSettingsBase> verwendet den Namen des Wrappers.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Klasse|Enthält den beschreibenden Text für eine Einstellungsgruppe primär von Tools zur Laufzeit und Entwurfszeit verwendet.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Beides|Gibt NULL oder mehr Verwaltbarkeit-Dienste, die für die Einstellungsgruppe oder die Eigenschaft bereitgestellt werden soll. Die verfügbaren Dienste werden vom beschrieben die <xref:System.Configuration.SettingsManageability> Enumeration.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Eigenschaft|Gibt an, dass eine Einstellung auf eine spezielle, vordefinierte Kategorie, z. B. eine Verbindungszeichenfolge gehört, die spezielle Verarbeitung durch den Einstellungsanbieter vorschlägt. Die vordefinierten Kategorien für dieses Attribut werden definiert, indem die <xref:System.Configuration.SpecialSetting> Enumeration.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Beides|Gibt einen bevorzugten Serialisierungsmechanismus für eine Einstellungsgruppe oder der Eigenschaft an. Die verfügbaren Serialisierungsmechanismen werden definiert, indem die <xref:System.Configuration.SettingsSerializeAs> Enumeration.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Eigenschaft|Gibt an, dass ein Einstellungsanbieter alle Upgrade Funktionalität der Anwendung für die markierte Eigenschaft deaktivieren sollten.|  
  
 *Klasse* gibt an, dass das Attribut nur auf eine Wrapperklasse für Anwendungseinstellungen angewendet werden kann. *Eigenschaft* gibt an, dass das Attribut nur auf Einstellungseigenschaften angewendet werden kann. *Beide* gibt an, dass das Attribut auf eine Ebene angewendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Vorgehensweise: Erstellen von Anwendungseinstellungen](http://msdn.microsoft.com/en-us/53b3af80-1c02-4e35-99c6-787663148945)
