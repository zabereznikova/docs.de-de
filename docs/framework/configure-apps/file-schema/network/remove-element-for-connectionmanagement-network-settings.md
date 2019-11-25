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
ms.openlocfilehash: 287e36dce65be7a002499d2cd22481018a1f4742
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089171"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<>-Element für connectionManagement entfernen (Netzwerkeinstellungen)
Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**entfernen >**

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
  
## <a name="remarks"></a>Hinweise  
 Das `remove`-Element entfernt den Verbindungs Verwaltungs Listeneintrag für den angegebenen Server.  
  
 Der Wert des `address` Attributs muss eine gültige IP-Adresse oder ein gültiger Hostname sein.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Verbindungs Verwaltungs Listeneinträge für den Server `www.adventure-works.com` entfernt. Anschließend wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
