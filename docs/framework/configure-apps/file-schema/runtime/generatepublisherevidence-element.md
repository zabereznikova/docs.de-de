---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caec297f8d0f6febad5cf46adb0a2658960c6bb1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663673"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > Element
Gibt an, ob die <xref:System.Security.Policy.Publisher> Laufzeit Beweise für Code Zugriffssicherheit (CAS) erstellt.  
  
 \<configuration>  
\<Lauf Zeit >  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die <xref:System.Security.Policy.Publisher> Laufzeit Beweise erstellt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Erstellt <xref:System.Security.Policy.Publisher> keine Beweise.|  
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
>  In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten. Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](../../../security/security-changes.md)".  
  
 Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu über <xref:System.Security.Policy.Publisher> prüfen, um einen Beweis für die Assembly zu erstellen. Die meisten Anwendungen benötigen <xref:System.Security.Policy.Publisher> jedoch standardmäßig keine Beweise. Die Standard-CAS-Richtlinie beruht <xref:System.Security.Policy.PublisherMembershipCondition>nicht auf dem. Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten <xref:System.Security.Permissions.PublisherIdentityPermission> CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für in einer teilweise vertrauenswürdigen Umgebung zu erfüllen. (Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)  
  
> [!NOTE]
>  Wir empfehlen, dass Dienste das `<generatePublisherEvidence>` -Element verwenden, um die Startleistung zu verbessern.  Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie das- `<generatePublisherEvidence>` Element verwendet wird, um die Überprüfung der CAS-Herausgeber Richtlinie für eine Anwendung zu deaktivieren  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
