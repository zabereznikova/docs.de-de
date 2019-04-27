---
title: <bypassTrustedAppStrongNames>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674206"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames>-Element
Gibt an, ob die Überprüfung von starken Namen für voll vertrauenswürdige Assemblys umgangen, die ein voll vertrauenswürdiges geladen <xref:System.AppDomain>.  
  
 \<configuration>  
\<runtime>  
\<bypassTrustedAppStrongNames>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Bypass-Funktion, die Überprüfung starke Namen für voll vertrauenswürdige Assemblys aktiviert ist. Wenn dieses Feature aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft werden, wenn die Assembly geladen wird. Die Standardeinstellung ist `true`.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Signaturen mit starkem Namen für voll vertrauenswürdige Assemblys werden nicht überprüft werden, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>. Dies ist die Standardeinstellung.|  
|`false`|Signaturen mit starkem Namen für voll vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>. Die Signatur mit starkem Namen wird nur auf Korrektheit der Signatur überprüft. Es wird nicht mit einem anderen starken Namens für eine Übereinstimmung verglichen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Das strong-Name-Bypass-Feature vermeidet den zusätzlichen Aufwand Überprüfung der Signatur mit starkem Namen der vollständig vertrauenswürdigen Assemblys.  
  
 Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:  
  
-   Voll vertrauenswürdig ohne die <xref:System.Security.Policy.StrongName> Beweise (beispielsweise `MyComputer` Zonenbeweis).  
  
-   Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>  
  
-   Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>  
  
-   Nicht verzögert signiert  
  
> [!NOTE]
>  Wenn die Bypass-Funktion für alle Anwendungen auf dem Computer deaktiviert wurde mithilfe eines Registrierungsschlüssels, hat diese Einstellung keine Auswirkungen. Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie das Verhalten angeben, das die Signatur mit starkem Namen für voll vertrauenswürdige Assemblys überprüft wird.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
