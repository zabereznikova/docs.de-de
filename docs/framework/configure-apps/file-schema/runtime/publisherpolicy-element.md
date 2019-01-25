---
title: '&lt;PublisherPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc33405d8fbb3e5f66be9ea2deb4545bd4ca0971
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620590"
---
# <a name="ltpublisherpolicygt-element"></a>&lt;PublisherPolicy&gt; Element
Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<dependentAssembly>  
\<publisherPolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`apply`|Gibt an, ob die Herausgeberrichtlinie angewendet werden soll.|  
  
## <a name="apply-attribute"></a>Attribut anwenden  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`yes`|Wendet die Verleger-Richtlinie. Dies ist die Standardeinstellung.|  
|`no`|Herausgeberrichtlinie wird nicht angewendet werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Bei einem Komponentenanbieter eine neue Version einer Assembly der Veröffentlichung kann der Anbieter eine Herausgeberrichtlinie enthalten, sodass Anwendungen, die die alte Version nun verwenden die neue Version verwenden. Um anzugeben, ob Herausgeberrichtlinie für eine bestimmte Assembly anzuwenden, fügen die  **\<PublisherPolicy >** Element in der  **\<DependentAssembly >** Element.  
  
 Die Standardeinstellung für die **anwenden** Attribut **Ja**. Festlegen der **anwenden** Attribut **keine** überschreibt alle vorherigen **Ja** Einstellungen für eine Assembly.  
  
 Berechtigung ist erforderlich, damit eine Anwendung explizit ignoriert Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy anwenden = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Konfigurationsdatei der Anwendung. Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>. Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deaktiviert die Herausgeberrichtlinie für die Assembly `myAssembly`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
