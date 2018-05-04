---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; Element
Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungsdomänengrenzen hinweg verwendet werden.  
  
 \<configuration>  
\<Common Language Runtime >  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime, COM-Interop anstelle von Remoting über Anwendungsdomänengrenzen hinweg verwendet werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Common Language Runtime wird Remoting über Anwendungsdomänengrenzen hinweg verwendet werden. Dies ist die Standardeinstellung.|  
|`true`|Die Common Language Runtime wird COM-Interop über Anwendungsdomänengrenzen hinweg verwendet werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Festlegen der `enabled` -Attribut `true`, die Common Language Runtime verhält sich wie folgt:  
  
-   Die Common Language Runtime nicht aufgerufen [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle, wenn ein [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) Schnittstelle wechselt in die Domäne über eine COM-Schnittstelle. Stattdessen erstellt er eine [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) um das Objekt.  
  
-   Die Common Language Runtime wird E_NOINTERFACE zurückgegeben, bei Erhalt des eine `QueryInterface` rufen Sie für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle für eine beliebige [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), die in dieser Domäne erstellt wurde.  
  
 Diese zwei Verhaltensweisen stellen Sie sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendung Domäne Grenzen verwenden COM- und COM-Interop anstelle von Remoting.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht angeben, dass die Common Language Runtime für COM-Interop-hinweg Isolation:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
