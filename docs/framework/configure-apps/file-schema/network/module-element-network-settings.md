---
title: '&lt;Modul&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 06c653d8759224e1112183a7e86e9797a97402af
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltmodulegt-element-network-settings"></a>&lt;Modul&gt; -Element (Netzwerkeinstellungen)
Fügt der Anwendung ein neues Proxymodul hinzu.  
  
 \<configuration>  
\<system.net>  
\<DefaultProxy >  
\<Modul >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`type`|Den vollqualifizierten Typnamen (erkennbar die <xref:System.Type.FullName%2A> Eigenschaft) und der Name der Assembly (angegeben durch die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die den Proxy implementiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="remarks"></a>Hinweise  
 Die `module` -Element registriert Proxyklassen, implementieren die <xref:System.Net.IWebProxy> Schnittstelle. Nach dem Registrieren der Proxyklasse `module` kann zum Anfordern von Informationen über den unterstützten Proxy verwendet werden.  
  
 Der Wert für die `type` Attribut muss der Klassenname des Moduls und den Namen der entsprechenden Dynamic Link Library (DLL).  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine benutzerdefinierte Proxyklasse registriert.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
