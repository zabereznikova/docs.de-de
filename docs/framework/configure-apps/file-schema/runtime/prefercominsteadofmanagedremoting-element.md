---
title: <PreferComInsteadOfManagedRemoting>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c79c76717acf7ff309375313b30534dd0aff9399
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920695"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<Prefercominsteadof managedremoting-> Element
Gibt an, ob die Laufzeit COM-Interop anstelle von Remoting für alle Aufrufe über Anwendungs Domänen Grenzen hinweg verwenden soll.  
  
 \<configuration>  
\<Lauf Zeit >  
\<PreferComInsteadOfManagedRemoting>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit COM-Interop anstelle eines Remoting über Anwendungs Domänen Grenzen hinweg verwenden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Laufzeit verwendet Remoting über Anwendungs Domänen Grenzen hinweg. Dies ist die Standardeinstellung.|  
|`true`|Die Laufzeit verwendet COM-Interop über Anwendungs Domänen Grenzen hinweg.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie das `enabled` -Attribut auf `true`festlegen, verhält sich die Laufzeit wie folgt:  
  
- Die Laufzeit ruft [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle nicht auf, wenn eine [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) -Schnittstelle über eine COM-Schnittstelle in die Domäne gelangt. Stattdessen wird ein [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) um das Objekt konstruiert.  
  
- Die Laufzeit gibt E_NOINTERFACE zurück, wenn Sie `QueryInterface` einen Aufruf für eine [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) -Schnittstelle für einen [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) empfängt, der in dieser Domäne erstellt wurde.  
  
 Diese beiden Verhalten stellen sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Anwendungs Domänen Grenzen hinweg com und COM-Interop anstelle von Remoting verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Common Language Runtime COM-Interop über Isolations Grenzen hinweg verwenden soll:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
