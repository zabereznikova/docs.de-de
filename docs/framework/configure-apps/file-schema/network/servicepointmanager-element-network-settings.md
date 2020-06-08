---
title: <servicePointManager>-Element (Netzwerkeinstellungen)
description: <servicePointManager>Mit dem Netzwerk Einstellungs Element werden Verbindungen zu den Optionen für Netzwerkressourcen in der .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: eb27716ec7c2936f32a7e4d4c983d1e175c4d044
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504523"
---
# <a name="servicepointmanager-element-network-settings"></a>\<servicePointManager>-Element (Netzwerkeinstellungen)
Konfiguriert Verbindungen mit Netzwerkressourcen.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a>Syntax  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`checkCertificateName`|Gibt an, ob das System überprüfen soll, ob der Name des Zertifikats mit dem Server Hostnamen übereinstimmt, bevor das Zertifikat verwendet wird. Der Standardwert lautet `true`.|  
|`checkCertificateRevocationList`|Gibt an, ob das System vor der Verwendung des Zertifikats überprüfen soll, ob das Zertifikat widerrufen wurde. Der Standardwert lautet `false`.|  
|`dnsRefreshTimeout`|Gibt an, wie lange die Auflösung von Domain Name Service (DNS) in Verbindung mit der Option "DNS Round Robin" in Millisekunden zwischengespeichert wird. Der Standardwert ist 120.000 Millisekunden (zwei Minuten).|  
|`enableDnsRoundRobin`|Gibt an, ob DNS-Auflösungen von Hostnamen mit mehreren IP-Adressen (Internet Protocol) alle Adressen oder nur den ersten zurückgeben. Der Standardwert lautet `false`.|  
|`encryptionPolicy`|Gibt die Verschlüsselungs Richtlinie an, die auf eine SSL/TLS-Sitzung auf einer-Instanz angewendet wird <xref:System.Net.ServicePointManager> . Die möglichen Werte entsprechen den Werten für die- <xref:System.Net.Security.EncryptionPolicy> Enumeration. <xref:System.Security.Authentication.CipherAlgorithmType.Null>Wenn die Verschlüsselungs Richtlinie auf festgelegt ist, ist die Verwendung von erforderlich `NoEncryption` . Der Standardwert lautet `RequireEncryption`.|  
|`expect100Continue`|Gibt an, ob Post-Methoden erwarten, dass eine `100-continue` Antwort vom Server empfangen wird. Der Standardwert lautet `true`.|  
|`useNagleAlgorithm`|Gibt an, ob vom Dienst Punkt-Manager gesteuerte Verbindungen den Nagle-Algorithmus verwenden. Der Standardwert lautet `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Netzwerkeinstellungsschema](index.md)
