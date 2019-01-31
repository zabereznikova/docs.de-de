---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f029131f5b10cc487021ee15e72552a26c0b04e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275846"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> Element
Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweis für die Codezugriffssicherheit (CAS).  
  
 \<configuration>  
\<runtime>  
\<generatePublisherEvidence>  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweise.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.|  
|`true`|Erstellt <xref:System.Security.Policy.Publisher> Beweise. Dies ist die Standardeinstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher, dieses Element hat keine Auswirkungen auf die Assembly in den Ladezeiten. Weitere Informationen finden Sie im Abschnitt "Security Policy Vereinfachung" in [Sicherheitsänderungen](../../../../../docs/framework/security/security-changes.md).  
  
 Die common Language Runtime (CLR) versucht zum Überprüfen der Authenticode-Signatur zur Ladezeit erstellen <xref:System.Security.Policy.Publisher> Beweis für die Assembly. Allerdings wird standardmäßig die meisten Anwendungen müssen nicht <xref:System.Security.Policy.Publisher> Beweise. Standard-CAS-Richtlinien beruht nicht auf die <xref:System.Security.Policy.PublisherMembershipCondition>. Vermeiden Sie die unnötige Start Kosten im Zusammenhang mit der Signatur des Herausgebers wird überprüft, es sei denn, Ihre Anwendung auf einem Computer mit benutzerdefinierten CAS-Richtlinie ausgeführt wird, oder zum Erfüllen der Anforderungen für die beabsichtigt ist <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung. (Anforderungen für Identitätsberechtigungen immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)  
  
> [!NOTE]
>  Es wird empfohlen, die Dienste verwenden die `<generatePublisherEvidence>` Element, um die startleistung zu verbessern.  Mit diesem Element können auch Verzögerungen zu vermeiden, die ein Timeout und den Abbruch des Dienststarts verursachen können.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `<generatePublisherEvidence>` Element So deaktivieren Sie die Verleger-CAS-Richtlinie für eine Anwendung überprüfen.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
