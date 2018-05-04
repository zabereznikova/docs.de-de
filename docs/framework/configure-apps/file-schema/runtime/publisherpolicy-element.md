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
ms.openlocfilehash: 2cc3b7220fe34f5dc049a3da71b160a88f82fdb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltpublisherpolicygt-element"></a>&lt;PublisherPolicy&gt; Element
Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.  
  
 \<configuration>  
\<Common Language Runtime >  
\<assemblyBinding>  
\<DependentAssembly >  
\<PublisherPolicy >  
  
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
|`yes`|Wendet die Richtlinie der Verleger. Dies ist die Standardeinstellung.|  
|`no`|Herausgeberrichtlinie ist nicht gültig.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Komponentenhersteller eine neue Version einer Assembly freigibt, kann der Hersteller eine Herausgeberrichtlinie enthalten, damit Anwendungen, die die alte Version jetzt verwenden die neue Version verwenden. Um anzugeben, ob Herausgeberrichtlinie für eine bestimmte Assembly anzuwenden, speichern die  **\<PublisherPolicy >** Element in der  **\<DependentAssembly >** Element.  
  
 Die Standardeinstellung für die **gelten** -Attribut ist **Ja**. Festlegen der **gelten** -Attribut **keine** überschreibt alle vorherigen **Ja** Einstellungen für eine Assembly.  
  
 Berechtigung ist erforderlich, damit eine Anwendung explizit ignorieren Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy gelten = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Anwendungskonfigurationsdatei. Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>. Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird für die Assembly deaktiviert Herausgeberrichtlinie `myAssembly`.  
  
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
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
