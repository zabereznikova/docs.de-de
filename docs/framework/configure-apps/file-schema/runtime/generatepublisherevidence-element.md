---
title: '&lt;"generatePublisherEvidence"&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f56bbef6ed6decf6be4246f649665db4cf0f766
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltgeneratepublisherevidencegt-element"></a>&lt;"generatePublisherEvidence"&gt; Element
Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweis für die Codezugriffssicherheit (CAS).  
  
 \<configuration>  
\<Common Language Runtime >  
\<"generatePublisherEvidence" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweis.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Erstellt keine <xref:System.Security.Policy.Publisher> Beweis.|  
|`true`|Erstellt <xref:System.Security.Policy.Publisher> Beweis. Dies ist die Standardeinstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher, dieses Element hat keine Auswirkungen auf die Assembly Ladezeiten. Weitere Informationen finden Sie im Abschnitt "Security Policy Vereinfachung" [Sicherheitsänderungen](../../../../../docs/framework/security/security-changes.md).  
  
 Die common Language Runtime (CLR) versucht, beim Überprüfen der Authenticode-Signatur zur Ladezeit erstellen <xref:System.Security.Policy.Publisher> Beweis für die Assembly. Allerdings wird standardmäßig die meisten Anwendungen müssen nicht <xref:System.Security.Policy.Publisher> Beweis. Standard-CAS-Richtlinie nicht auf beruht die <xref:System.Security.Policy.PublisherMembershipCondition>. Vermeiden Sie die Kosten für unnötige Start bei der Überprüfung der Signatur des Herausgebers, wenn Ihre Anwendung auf einem Computer mit benutzerdefinierten CAS-Richtlinie ausgeführt wird oder Forderungen nach erfüllen beabsichtigt ist <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung. (Anforderungen für Identitätsberechtigungen immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung ausgeführt.)  
  
> [!NOTE]
>  Es wird empfohlen, dass Dienste verwenden die `<generatePublisherEvidence>` Element, um die startleistung zu verbessern.  Mit diesem Element können auch Verzögerungen zu vermeiden, die ein Timeout und den Abbruch des Dienststarts verursachen kann.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `<generatePublisherEvidence>` -Element nach deaktivieren Verleger CAS-Richtlinie für eine Anwendung.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
