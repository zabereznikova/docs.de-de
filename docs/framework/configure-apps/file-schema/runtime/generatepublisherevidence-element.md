---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "81645359"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence>-Element
Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise für Code Zugriffssicherheit (CAS) erstellt.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise erstellt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
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
  
## <a name="remarks"></a>Bemerkungen  
  
> [!NOTE]
> In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten. Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)".  
  
 Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu überprüfen, um einen <xref:System.Security.Policy.Publisher> Beweis für die Assembly zu erstellen. Die meisten Anwendungen benötigen jedoch standardmäßig keine <xref:System.Security.Policy.Publisher> Beweise. Die Standard-CAS-Richtlinie beruht nicht auf dem <xref:System.Security.Policy.PublisherMembershipCondition> . Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung zu erfüllen. (Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)  
  
> [!NOTE]
> Wir empfehlen, dass Dienste das- `<generatePublisherEvidence>` Element verwenden, um die Startleistung zu verbessern.  Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
