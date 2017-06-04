---
title: "Attribute f&#252;r Anwendungseinstellungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungseinstellungen [Windows Forms], Attribute"
  - "Attribute [Windows Forms], Anwendungseinstellungen"
  - "Wrapperklassen, Anwendungseinstellungen"
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Attribute f&#252;r Anwendungseinstellungen
Die Architektur der Anwendungseinstellungen bietet zahlreiche Attribute, die entweder auf die Wrapperklasse der Anwendungseinstellungen oder ihre einzelnen Eigenschaften angewendet werden können.  Diese Attribute werden zur Laufzeit von der Infrastruktur der Anwendungseinstellungen überprüft, häufig speziell der Anbieter der Einstellungen, um sie an die Anforderungen des benutzerdefinierten Wrappers anzupassen.  
  
 In der folgenden Tabelle werden die Attribute aufgelistet, die auf die Wrapperklasse der Anwendungseinstellungen, die einzelnen Eigenschaften dieser Klasse oder beides angewendet werden können.  Definitionsgemäß muss auf jede Einstellungseigenschaft nur ein einziges Bereichsattribut – **UserScopedSettingAttribute** oder **ApplicationScopedSettingAttribute** – angewendet werden.  
  
> [!NOTE]
>  Ein benutzerdefinierter Einstellungsanbieter, der von der <xref:System.Configuration.SettingsProvider>\-Klasse abgeleitet wird, ist nur zum Erkennen der folgenden drei Attribute erforderlich: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute** und **DefaultSettingValueAttribute**.  
  
|Attribut|Target|Beschreibung|  
|--------------|------------|------------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Beides|Gibt den kurzen Namen des Einstellungsanbieters an, der zur Beibehaltung verwendet werden soll.<br /><br /> Wenn dieses Attribut nicht angegeben wird, wird vom Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider> ausgegangen.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als benutzerspezifische Anwendungseinstellung.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Beides|Definiert eine Eigenschaft als anwendungsspezifische Einstellung.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Property|Gibt eine Zeichenfolge an, die vom Anbieter in den fest definierten Standardwert für diese Eigenschaft deserialisiert werden kann.<br /><br /> Dieses Attribut ist für <xref:System.Configuration.LocalFileSettingsProvider> nicht erforderlich und überschreibt jeden Wert, der von diesem Attribut bereitgestellt wird, wenn bereits ein Wert erhalten bleibt.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Property|Stellt den beschreibenden Text für eine einzelne Einstellung bereit, die hauptsächlich von Tools zur Laufzeit und zur Entwurfszeit verwendet wird.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Klasse|Stellt einen expliziten Namen für eine Einstellungsgruppe bereit.  Wenn dieses Attribut fehlt, verwendet <xref:System.Configuration.ApplicationSettingsBase> den Wrapperklassennamen.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Klasse|Stellt den beschreibenden Text für eine Einstellungsgruppe bereit, die hauptsächlich von Tools zur Laufzeit und zur Entwurfszeit verwendet wird.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Beides|Gibt null oder mehr Verwaltungsdienste an, die für die Einstellungsgruppe oder die Eigenschaft bereitgestellt werden sollten.  Die verfügbaren Dienste werden von der <xref:System.Configuration.SettingsManageability>\-Enumeration beschrieben.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Property|Gibt an, dass eine Einstellung zu einer bestimmten, vordefinierten Kategorie, z. B. eine Kategoriezeichenfolge, gehört, die eine spezielle Verarbeitung durch den Einstellungsanbieter vorsieht.  Die vordefinierten Kategorien für dieses Attribut werden von der <xref:System.Configuration.SpecialSetting>\-Enumeration definiert.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Beides|Legt einen bevorzugten Serialisierungsmechanismus für eine Einstellungsgruppe oder eine Eigenschaft fest.  Die verfügbaren Serialisierungsmechanismen werden von der <xref:System.Configuration.SettingsSerializeAs>\-Enumeration definiert.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Property|Legt fest, dass ein Einstellungsanbieter sämtliche Funktionen zur Anwendungsaktualisierung für die markierte Eigenschaft deaktivieren sollte.|  
  
 *Klasse* gibt an, dass das Attribut nur auf eine Wrapperklasse für Anwendungseinstellungen angewendet werden kann.  *Eigenschaft* gibt an, dass das Attribut nur auf Einstellungseigenschaften angewendet werden kann.  *Beides* gibt an, dass das Attribut auf beiden Ebenen angewendet werden kann.  
  
## Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)   
 [How to: Create Application Settings](http://msdn.microsoft.com/de-de/53b3af80-1c02-4e35-99c6-787663148945)