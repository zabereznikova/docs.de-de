---
title: <add>-Element für connectionManagement (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: a7a4cfe952a32c859a113f0903696fec3681f800
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267620"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a>\<Hinzufügen >-Element für ConnectionManagement (Netzwerkeinstellungen)
Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.  
  
 \<configuration>  
\<system.net>  
\<connectionManagement>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`address`|Eine Zeichenfolge, die eine IP-Adresse oder einen DNS-Namen beschreibt.|  
|`maxconnection`|Die maximale Anzahl von Verbindungen, die für einen Server zulässig sind. Wenn keine Angabe erfolgt, wird der Standardwert "2" verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des `address`-Attributs muss entweder ein Sternchen zur Angabe aller Verbindungen oder eine Zeichenfolge im Format `<schema>://<idn_hostname>[:<port>]` sein.  
  
 Enthält der an HTTP-APIs übergebene URI Unicode, wird der Name intern mit <xref:System.Uri.DnsSafeHost%2A> umgewandelt, wodurch möglicherweise eine Punycode-Zeichenfolge zurückgegeben wird (das Verhalten ist von der aktuellen IDN-Konfiguration abhängig).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Anwendung für die Verwendung von vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
