---
title: <idn>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: f45922ecd5f7476362aab5348d91415d8e31c53f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195401"
---
# <a name="idn-element-uri-settings"></a>\<idn>-Element (URI-Einstellungen)

Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird.
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
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
|`enabled`|Gibt an, ob die IDN (Internationalized Domain Name)-Verarbeitung auf einen Domänen Namen angewendet wird. der Standardwert ist "None".|  

### <a name="child-elements"></a>Untergeordnete Elemente

Keine
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.|  

## <a name="remarks"></a>Bemerkungen

Die vorhandene <xref:System.Uri> Klasse wurde in .NET Framework 3,5 erweitert. 3,0 SP1 und 2,0 SP1 mit Unterstützung für International Resource Identifier (IRI) und Internationalized Domain Names (IDN). Aktuelle Benutzer sehen keine Änderung des Verhaltens von .NET Framework 2,0, es sei denn, Sie aktivieren speziell IRI-und IDN-Unterstützung. Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.

Die folgenden beiden Änderungen sind erforderlich, um die Unterstützung für IRI zu aktivieren:

1. Fügen Sie die folgende Zeile in die Datei machine.config im Verzeichnis .NET Framework 2,0 ein:
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Geben Sie an, ob die IDN-Verarbeitung (Internationalized Domain Name) auf den Domänen Namen angewendet werden soll und ob IRI-Regeln angewendet werden sollen. Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.

 Es gibt drei mögliche Werte für IDN, abhängig von den verwendeten DNS-Servern:

- IDN aktiviert = alle  

     Durch diesen Wert werden alle Unicode-Domänennamen in ihre Punycode-Entsprechungen (IDN-Namen) konvertiert.

- IDN aktiviert = AllExceptIntranet

     Dieser Wert konvertiert alle Unicode-Domänen Namen, die nicht im lokalen Intranet sind, in die Verwendung der Punycode-Entsprechungen (IDN-Namen). In diesem Fall sollten die DNS-Server, die für das Intranet verwendet werden, die Auflösung von Unicode-Namen unterstützen, um internationale Namen im lokalen Intranet zu verarbeiten.

- IDN aktiviert = None

     Durch diesen Wert werden keine Unicode-Domänennamen in ihre Punycode-Entsprechungen konvertiert. Dies ist der Standardwert, der dem .NET Framework 2.0-Verhalten entspricht.

 Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert. Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“. So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).

### <a name="configuration-files"></a>Konfigurationsdateien

Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Konfiguration, die von der- <xref:System.Uri> Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird:

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
