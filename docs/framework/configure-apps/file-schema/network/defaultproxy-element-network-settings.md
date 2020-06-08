---
title: <defaultProxy>-Element (Netzwerkeinstellungen)
description: <defaultProxy>Mit dem Netzwerk Einstellungs Element wird der HTTP-Proxy Server (Hypertext Transfer Protocol) im .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 915fdc96dbd4d417f9c9e6aa3ff96de3026491ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504601"
---
# <a name="defaultproxy-element-network-settings"></a>\<defaultProxy>-Element (Netzwerkeinstellungen)
Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|`enabled`|Gibt an, ob ein Webproxy verwendet wird. Der Standardwert lautet `true`.|  
|`useDefaultCredentials`|Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden. Der Standardwert lautet `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.|  
|[Mond](module-element-network-settings.md)|Fügt der Anwendung ein neues Proxymodul hinzu.|  
|[Proxy](proxy-element-network-settings.md)|Definiert einen Proxyserver.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet. Dieses Verhalten unterscheidet sich von .NET Framework 1.1.  
  
 Eine-Ausnahme wird ausgelöst, wenn das [Module](module-element-network-settings.md) -Element einen nicht öffentlichen Typ angibt, der Typ nicht von der-Klasse abgeleitet wird <xref:System.Net.IWebProxy> , eine Ausnahme vom Parameter losen Konstruktor dieses Objekts aufgetreten ist oder beim Abrufen des vom System angegebenen Standard Proxys eine Ausnahme aufgetreten ist. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff und contoso.com umgangen.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
