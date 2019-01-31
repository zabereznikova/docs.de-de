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
ms.openlocfilehash: 3a18f9eb3d38ef272b7a4df58d8588b622662184
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277549"
---
# <a name="servicepointmanager-element-network-settings"></a>\<ServicePointManager >-Element (Netzwerkeinstellungen)
Konfiguriert die Verbindungen mit Netzwerkressourcen.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<servicePointManager>  
  
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
|`checkCertificateName`|Gibt an, ob das System, dass der Name des Zertifikats den Serverhostnamen entspricht, bevor Sie mithilfe des Zertifikats überprüft werden soll. Der Standardwert ist `true`.|  
|`checkCertificateRevocationList`|Gibt an, ob das System eine Überprüfung, ob das Zertifikat widerrufen wurde, bevor Sie mit dem Zertifikat. Der Standardwert ist `false`.|  
|`dnsRefreshTimeout`|Gibt wie lange Dienst DNS (Domain Name), dass Sie Lösungen zwischengespeichert werden in Verbindung mit dem DNS-Round-Robin-Option in Millisekunden an. Der Standardwert ist 120.000 Millisekunden (zwei Minuten).|  
|`enableDnsRoundRobin`|Gibt an, ob die DNS-Auflösungen des Hosts Namen mit mehreren IP (Internet Protocol)-Adressen zurückgegeben, alle Adressen oder nur die erste. Der Standardwert ist `false`.|  
|`encryptionPolicy`|Gibt an, die Verschlüsselungsrichtlinie auf eine SSL/TLS-Sitzung angewendet wird, auf eine <xref:System.Net.ServicePointManager> Instanz. Die möglichen Werte entsprechen den Werten für die <xref:System.Net.Security.EncryptionPolicy> Enumeration. Die Verwendung von <xref:System.Security.Authentication.CipherAlgorithmType.Null> ist erforderlich, wenn die Verschlüsselungsrichtlinie, um festgelegt ist `NoEncryption`. Der Standardwert ist `RequireEncryption`.|  
|`expect100Continue`|Gibt an, ob die POST-Methoden erwarten soll zum Empfangen einer `100-continue` Antwort vom Server. Der Standardwert ist `true`.|  
|`useNagleAlgorithm`|Gibt an, ob den Nagle-Algorithmus, Verbindungen, die von der Point-Manager gesteuert verwenden. Der Standardwert ist `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
