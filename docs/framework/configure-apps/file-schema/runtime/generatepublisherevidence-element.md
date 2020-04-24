---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645359"
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
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob <xref:System.Security.Policy.Publisher> die Laufzeit Beweise erstellt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
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
> In .NET Framework 4 und höher hat dieses Element keine Auswirkungen auf die Ladezeiten der Assembly. Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinien" unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Laufzeiteinstellungsschema](index.md)
- [Konfigurationsdateischema](../index.md)
