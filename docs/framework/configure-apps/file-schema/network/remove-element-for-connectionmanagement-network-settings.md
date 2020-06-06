---
title: <remove>-Element für connectionManagement (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154737"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<remove>-Element für connectionManagement (Netzwerkeinstellungen)
Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Syntax  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`address`|Eine IP-Adresse oder ein DNS-Name.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `remove` Element entfernt den Verbindungs Verwaltungs Listeneintrag für den angegebenen Server.  
  
 Der Wert des `address` -Attributs muss eine gültige IP-Adresse oder ein gültiger Hostname sein.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Verbindungs Verwaltungs Listeneinträge für den-Server entfernt `www.adventure-works.com` . Anschließend wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Netzwerkeinstellungsschema](index.md)
