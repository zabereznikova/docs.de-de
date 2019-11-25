---
title: <servicePointManager>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089130"
---
# <a name="servicepointmanager-element-network-settings"></a>\<ServicePointManager-> Element (Netzwerkeinstellungen)
Konfiguriert Verbindungen mit Netzwerkressourcen.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einstellungen**](settings-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ServicePointManager >**

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
|`checkCertificateName`|Gibt an, ob das System überprüfen soll, ob der Name des Zertifikats mit dem Server Hostnamen übereinstimmt, bevor das Zertifikat verwendet wird. Der Standardwert ist `true`sein.|  
|`checkCertificateRevocationList`|Gibt an, ob das System vor der Verwendung des Zertifikats überprüfen soll, ob das Zertifikat widerrufen wurde. Der Standardwert ist `false`sein.|  
|`dnsRefreshTimeout`|Gibt an, wie lange die Auflösung von Domain Name Service (DNS) in Verbindung mit der Option "DNS Round Robin" in Millisekunden zwischengespeichert wird. Der Standardwert ist 120.000 Millisekunden (zwei Minuten).|  
|`enableDnsRoundRobin`|Gibt an, ob DNS-Auflösungen von Hostnamen mit mehreren IP-Adressen (Internet Protocol) alle Adressen oder nur den ersten zurückgeben. Der Standardwert ist `false`sein.|  
|`encryptionPolicy`|Gibt die Verschlüsselungs Richtlinie an, die auf eine SSL/TLS-Sitzung auf einer <xref:System.Net.ServicePointManager>-Instanz angewendet wird. Die möglichen Werte entsprechen den Werten für die <xref:System.Net.Security.EncryptionPolicy>-Enumeration. Die Verwendung von <xref:System.Security.Authentication.CipherAlgorithmType.Null> ist erforderlich, wenn die Verschlüsselungs Richtlinie auf `NoEncryption`festgelegt ist. Der Standardwert ist `RequireEncryption`sein.|  
|`expect100Continue`|Gibt an, ob Post-Methoden erwarten, dass vom Server eine `100-continue`-Antwort empfangen wird. Der Standardwert ist `true`sein.|  
|`useNagleAlgorithm`|Gibt an, ob vom Dienst Punkt-Manager gesteuerte Verbindungen den Nagle-Algorithmus verwenden. Der Standardwert ist `true`sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
