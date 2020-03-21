---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154113"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> Element
Gibt an, ob <xref:System.Security.Policy.Publisher> die Laufzeit Beweise für die Codezugriffssicherheit (Code Access Security, CAS) erstellt.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob <xref:System.Security.Policy.Publisher> die Laufzeit Beweise erstellt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.|  
|`true`|Erstellt <xref:System.Security.Policy.Publisher> Beweise. Dies ist die Standardoption.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!NOTE]
> In .NET Framework 4 und höher hat dieses Element keine Auswirkungen auf die Ladezeiten der Assembly. Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinien" unter [Sicherheitsänderungen](../../../security/security-changes.md).  
  
 Die Common Language Runtime (CLR) versucht, die Authenticode-Signatur zum Zeitpunkt des Ladens zu überprüfen, um Beweise für die Assembly zu erstellen. <xref:System.Security.Policy.Publisher> Standardmäßig benötigen <xref:System.Security.Policy.Publisher> die meisten Anwendungen jedoch keine Beweise. Die Standard-CAS-Richtlinie <xref:System.Security.Policy.PublisherMembershipCondition>verlässt sich nicht auf die . Sie sollten die unnötigen Startkosten vermeiden, die mit der Überprüfung der Herausgebersignatur verbunden sind, es <xref:System.Security.Permissions.PublisherIdentityPermission> sei denn, Die Anwendung wird auf einem Computer mit benutzerdefinierten CAS-Richtlinien ausgeführt oder beabsichtigt, Anforderungen für eine umgebung mit teilweisem Vertrauen zu erfüllen. (Anforderungen an Identitätsberechtigungen sind in einer Umgebung mit voller Vertrauenswürdigkeit immer erfolgreich.)  
  
> [!NOTE]
> Es wird empfohlen, `<generatePublisherEvidence>` dass Dienste das Element verwenden, um die Startleistung zu verbessern.  Die Verwendung dieses Elements kann auch dazu beitragen, Verzögerungen zu vermeiden, die zu einem Timeout und zum Abbruch des Dienststarts führen können.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<generatePublisherEvidence>` wie sie das Element verwenden, um die Überprüfung auf CAS-Herausgeberrichtlinie für eine Anwendung zu deaktivieren.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
