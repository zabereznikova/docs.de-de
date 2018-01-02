---
title: '&lt;IDN&gt; Element (Uri-Einstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 44e2db95ec354fff4356a3619fa8230faf67544d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltidngt-element-uri-settings"></a>&lt;IDN&gt; Element (Uri-Einstellungen)
Gibt an, ob Internationalized Domain Name (IDN) Analyse an den Domänennamen angewendet wird.  
  
## <a name="schema-hierarchy"></a>Schemahierarchie  
 [\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI >-Element (Uri-Einstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<IDN >](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|`enabled`|Gibt bei Anwendung auf einen Domänennamen Internationalized Domain Name (IDN) Analyse der Standardwert none ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework Webadressen ausgedrückt mit uniform Resource Identifier (URIs) behandelt.|  
  
## <a name="remarks"></a>Hinweise  
 Die vorhandene <xref:System.Uri> Klasse in .NET Framework 3.5 erweitert wurde. 3.0 SP1 und 2.0 SP1 mit Unterstützung für International Resource Identifiers (IRI) und internationale Domänennamen (IDN). Aktuellen Benutzer sehen keine Änderungen des Verhaltens gegenüber den .NET Framework 2.0, es sei denn, sie explizit IRI und IDN aktivieren unterstützen. Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.  
  
 Um die Unterstützung für IRI aktivieren, sind die folgenden zwei Änderungen erforderlich:  
  
1.  Fügen Sie die folgende Zeile auf die Datei "Machine.config" im .NET Framework 2.0-Verzeichnis  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Geben Sie, ob Sie, dass Internationalized Domain Name (IDN) zu analysieren, die auf den Domänennamen angewendet und gibt an, ob die IRI-Analyse Regeln angewendet werden soll. Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.  
  
 Es gibt drei mögliche Werte für IDN abhängig von den DNS-Servern, die verwendet werden:  
  
-   IDN aktiviert = All  
  
     Dieser Wert wird alle Unicode-Domänennamen in ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.  
  
-   IDN aktiviert = AllExceptIntranet  
  
     Dieser Wert wird allen Unicode-Domänennamen nicht auf dem lokalen Intranet verwenden Sie die Punycode-Entsprechungen (IDN-Namen) konvertiert. In diesem Fall sollte die DNS-Server, die für das Intranet verwendet werden um internationale Namen im lokalen Intranet zu behandeln, Unicode-namensauflösung unterstützen.  
  
-   IDN aktiviert = keine  
  
     Dieser Wert keine Unicode-Domänennamen mit Punycode konvertiert werden. Dies ist der Standardwert, der mit dem .NET Framework 2.0-Verhalten konsistent ist.  
  
 Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert. Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“. So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).  
  
### <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Konfiguration von verwendet die <xref:System.Uri> Klasse IRI-Analyse und IDN-Namen unterstützt.  
  
### <a name="code"></a>Code  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
