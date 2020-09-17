---
title: WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: dbd33869de6b1ecee6406dfeede88afc4eca07f1
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720490"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)

Das WS-AtomicTransaction-Konfigurationsdienstprogramm wird zur Konfiguration von grundlegenden WS-AtomicTransaction-Unterstützungseinstellungen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Bemerkungen

 Dieses Befehlszeilen Tool kann verwendet werden, um grundlegende WS-AT-Einstellungen nur auf einem lokalen Computer zu konfigurieren. Wenn Sie Einstellungen auf lokalen Computern und Remote Computern konfigurieren müssen, sollten Sie das MMC-Snap-in verwenden, wie [unter Konfigurieren der WS-Atomic Transaction-Unterstützung](./feature-details/configuring-ws-atomic-transaction-support.md)beschrieben.  
  
 Das Befehlszeilen Tool befindet sich im Windows SDK Installationspfad:
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe
  
 In der folgenden Tabelle werden die Optionen angezeigt, die mit dem WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe) verwendet werden können.  
  
> [!NOTE]
> Wenn Sie ein SSL-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL-Zertifikat überschrieben, das diesem Port zugeordnet ist (sofern vorhanden).  
  
|Tastatur|BESCHREIBUNG|  
|-------------|-----------------|  
|Buchhaltungs\<account,>|Gibt eine durch Trennzeichen getrennte Liste von Konten an, die von WS-AtomicTransaction verwendet werden können. Die Gültigkeit dieser Konten wird nicht überprüft.|  
|-accountsCerts: \<thumb>&#124; "issuer\subjetname", >|Gibt eine durch Trennzeichen getrennte Liste von Zertifikaten an, die von WS-AtomicTransaction verwendet werden können. Die Zertifikate werden vom Fingerabdruck oder vom Issuer\SubjectName-Paar angegeben. Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|-endpointCert: <Computer&#124;\<thumb>&#124; "issuer\subjetname" >|Verwendet das Computerzertifikat oder ein anderes lokales Endpunktzertifikat, das vom Fingerabdruck oder Issuer\SubjectName-Paar angegeben wird. Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|MaxTimeout\<sec>|Gibt das maximale Timeout in Sekunden an. Gültige Werte sind 0 bis 3600.|  
|Netzwerk\<enable&#124;disable>|Aktiviert oder deaktiviert die WS-AtomicTransaction-Netzwerkunterstützung.|  
|Port\<portNum>|Legt den HTTPS-Anschluss für WS-AtomicTransaction fest.<br /><br /> Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert. Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.<br /><br /> Wenn Sie die Firewall nach der Konfiguration von WS-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben. Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS-AT ohne zusätzliche Eingabe ausgeführt.|  
|Zeit\<sec>|Gibt das Standardtimeout in Sekunden an. Gültige Werte reichen von 1 bis 3600.|  
|traceActivity\<enable&#124;disable>|Aktiviert oder deaktiviert die Ablaufverfolgung von Aktivitätsereignissen.|  
|-TraceLevel: \<Off&#124;Error&#124;Critical&#124;Warning&#124;Information&#124; Verbose&#124;All> }|Gibt die Ablaufverfolgungsebene an.|  
|-tracePII:\<enable&#124;disable>|Aktiviert oder deaktiviert die Ablaufverfolgung von persönlich identifizierbaren Informationen.|  
|-TraceProp:\<enable&#124;disable>|Aktiviert oder deaktiviert die Ablaufverfolgung von Propagierungsereignissen.|  
|-restart|Startet MSDTC neu, um Änderungen sofort zu aktivieren. Wenn dies nicht angegeben wird, werden die Änderungen erst wirksam, wenn MSDTC neu gestartet wird.|  
|-show|Zeigt die aktuellen WS-AtomicTransaction-Protokolleinstellungen an.|  
|Servers\<virtualServer>|Gibt den DTC-Ressourcenclusternamen an.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von WS-AtomicTransaction](./feature-details/using-ws-atomictransaction.md)
- [Konfigurieren der WS-AtomicTransaction-Unterstützung](./feature-details/configuring-ws-atomic-transaction-support.md)
