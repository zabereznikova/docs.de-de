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
ms.openlocfilehash: 3fb198d6a19e25df4c86186d35aab3330c53121c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252768"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames>-Element
Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, <xref:System.AppDomain>die in eine vollständige Vertrauenswürdigkeit geladen werden.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet. Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird. Die Standardeinstellung ist `true`.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden. Dies ist die Standardeinstellung.|  
|`false`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in <xref:System.AppDomain>eine voll vertrauenswürdige Assembly geladen werden. Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.  
  
 Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:  
  
- Voll vertrauenswürdig ohne <xref:System.Security.Policy.StrongName> den Beweis (z. b `MyComputer` . hat einen Zonen Nachweis).  
  
- Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>  
  
- Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>  
  
- Nicht verzögert signiert  
  
> [!NOTE]
> Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen. Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
