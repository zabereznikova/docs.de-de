---
title: <connectionManagement>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154893"
---
# <a name="connectionmanagement-element-network-settings"></a>\<connectionManagement>-Element (Netzwerkeinstellungen)
Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a>Syntax  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Hinzufügen](add-element-for-connectionmanagement-network-settings.md)|Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.|  
|[Klar](clear-element-for-connectionmanagement-network-settings.md)|Löscht die Verbindungsverwaltungsliste.|  
|[Entfernen](remove-element-for-connectionmanagement-network-settings.md)|Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungsverwaltungsliste.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `connectionManagement` Element definiert die maximale Anzahl von Verbindungen zu einem Server oder einer Gruppe von Servern.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Anwendung so `www.contoso.com` konfiguriert, dass sie vier Verbindungen zum Server und zwei Verbindungen zu allen anderen Servern verwendet.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Netzwerkeinstellungsschema](index.md)
