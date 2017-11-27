---
title: Netzwerkeinstellungsschema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ca4a0000d85c8fbac9a723beeda51f9c7886ed8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="network-settings-schema"></a>Netzwerkeinstellungsschema
Netzwerkeinstellungen geben an, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden. Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<system.Net>-Elements (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<authenticationModules>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Gibt die Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.|  
|[\<connectionManagement>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit Internethosts an.|  
|[\<defaultProxy>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Gibt den Proxyserver an, der für HTTP-Anforderungen an das Internet verwendet wird.|  
|[\<mailSettings>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Enthält Einstellungen für E-Mail-Sendeoptionen.|  
|[\<requestCaching>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.|  
|[\<requestCaching>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.|  
|[\<webRequestModules>-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die Module an, die zum Anfordern von Informationen von Internethosts verwendet werden.|  
  
 URI-Einstellungen geben an, wie .NET Framework Webadressen behandelt, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden. Die folgende Tabelle beschreibt die Funktion der einzelnen untergeordneten Konfigurationselemente des [\<Uri>-Elements (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<idn>-Element (URI-Einstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.|  
|[\<iriParsing>-Element (URI-Einstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Ressourcenbezeichner (International Resource Identifier, IRI) auf <xref:System.Uri> angewendet wird und ob die IRI-Analyseregeln angewendet werden sollen.|  
|[\<schemeSettings>-Element (URI-Einstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Internetanwendungen](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
