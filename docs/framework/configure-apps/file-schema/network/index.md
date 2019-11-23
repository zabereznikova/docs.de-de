---
title: Netzwerkeinstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698148"
---
# <a name="network-settings-schema"></a>Netzwerkeinstellungsschema
Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.

Die \<System. net > Einstellungen geben an, wie der .NET Framework eine Verbindung mit dem Netzwerk herstellt. Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<system.Net>-Elements (Netzwerkeinstellungen)](system-net-element-network-settings.md).  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<authenticationModules>-Element (Netzwerkeinstellungen)](authenticationmodules-element-network-settings.md)|Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.|  
|[\<connectionManagement>-Element (Netzwerkeinstellungen)](connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit Internethosts an.|  
|[\<defaultProxy>-Element (Netzwerkeinstellungen)](defaultproxy-element-network-settings.md)|Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.|  
|[\<mailSettings>-Element (Netzwerkeinstellungen)](mailsettings-element-network-settings.md)|Enthält Einstellungen für E-Mail-Sendeoptionen.|  
|[\<requestCaching>-Element (Netzwerkeinstellungen)](requestcaching-element-network-settings.md)|Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.|  
|[\<webRequestModules>-Element (Netzwerkeinstellungen)](webrequestmodules-element-network-settings.md)|Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.|  
  
Die \<-URI-> Einstellungen geben an, wie die .NET Framework Webanwendungen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden. In der folgenden Tabelle wird die Funktion der einzelnen untergeordneten Konfigurationselemente unter dem [\<-URI >-Element (URI-Einstellungen)](uri-element-uri-settings.md)beschrieben.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<idn>-Element (URI-Einstellungen)](idn-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.|  
|[\<iriParsing>-Element (URI-Einstellungen)](iriparsing-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.|  
|[\<schemeSettings>-Element (URI-Einstellungen)](schemesettings-element-uri-settings.md)|Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Internetanwendungen](../../../network-programming/configuring-internet-applications.md)
- [Konfigurationsdateischema](../index.md)
