---
title: <add>-Element für authenticationModules (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: a46e6af97f37974805812fb0d19801d618eee4d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705154"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a>\<Hinzufügen >-Element für AuthenticationModules (Netzwerkeinstellungen)
Ein Modul für die Authentifizierung hinzugefügt der Anwendung.  
  
 \<configuration>  
\<system.net>  
\<authenticationModules>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`type`|Den vollqualifizierten Typnamen (angegeben durch die <xref:System.Type.FullName%2A> Eigenschaft) und den Assemblynamen (erkennbar der <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft) und durch ein Komma getrennt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Gibt die Module, die zum Authentifizieren von netzwerkanforderungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `add` -Element fügt ein Authentifizierungsmodul an das Ende der Liste der registrierten Authentifizierungsmodule. Authentifizierungsmodule werden in der Reihenfolge aufgerufen, in denen sie zur Liste hinzugefügt wurden.  
  
 Der Wert für die `type` Attribut sollte einen gültigen Typnamen und den entsprechenden Assemblynamen, die durch ein Komma getrennt sein.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Standard-Authentifizierungsmodule. Sie sollten die Werte für die Version und ' PublicKeyToken ' machen durch die richtigen Werte für das angegebene Modul ersetzen.  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
