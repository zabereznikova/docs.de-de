---
title: WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: 161ac59e64e1a933049ed36ebb7140901686929c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425269"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)
Das WS-AtomicTransaction-Konfigurationsdienstprogramm wird zur Konfiguration von grundlegenden WS-AtomicTransaction-Unterstützungseinstellungen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Befehlszeilentool kann nur dazu verwendet werden, grundlegende WS-AT-Einstellungen auf einem lokalen Computer zu konfigurieren. Wenn Sie Einstellungen auf lokalen Computern und Remote Computern konfigurieren müssen, sollten Sie das MMC-Snap-in verwenden, wie [unter Konfigurieren der WS-Atomic Transaction-Unterstützung](./feature-details/configuring-ws-atomic-transaction-support.md)beschrieben.  
  
 Das Befehlszeilentool befindet sich im Windows SDK-Installationspfad:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe  
  
 Wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ausführen, müssen Sie vor dem Ausführen von WsatConfig.exe ein Update herunterladen. Weitere Informationen zu diesem Update finden Sie unter [Update for Commerce Server 2007 (KB912817)](https://go.microsoft.com/fwlink/?LinkId=95340) und [Availability of Windows XP com+ Hotfixrollup Package 13](https://go.microsoft.com/fwlink/?LinkId=95341).  
  
 In der folgenden Tabelle werden die Optionen angezeigt, die mit dem WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe) verwendet werden können.  
  
> [!NOTE]
> Wenn Sie ein SSL-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL-Zertifikat überschrieben, das diesem Port zugeordnet ist (sofern vorhanden).  
  
|Optionen|Beschreibung|  
|-------------|-----------------|  
|-Konten: \<konto, >|Gibt eine durch Trennzeichen getrennte Liste von Konten an, die von WS-AtomicTransaction verwendet werden können. Die Gültigkeit dieser Konten wird nicht überprüft.|  
|-accountsCerts: \<thumb >&#124;"issuer\subjetname", >|Gibt eine durch Trennzeichen getrennte Liste von Zertifikaten an, die von WS-AtomicTransaction verwendet werden können. Die Zertifikate werden vom Fingerabdruck oder vom Issuer\SubjectName-Paar angegeben. Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|-endpointCert: < Computer&#124;\<thumb >&#124;"issuer\subjetname" >|Verwendet das Computerzertifikat oder ein anderes lokales Endpunktzertifikat, das vom Fingerabdruck oder Issuer\SubjectName-Paar angegeben wird. Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|-MaxTimeout: \<sek >|Gibt das maximale Timeout in Sekunden an. Gültige Werte sind 0 bis 3600.|  
|-Network: \<enable&#124;deaktivieren >|Aktiviert oder deaktiviert die WS-AtomicTransaction-Netzwerkunterstützung.|  
|-Port: \<portnum >|Legt den HTTPS-Anschluss für WS-AtomicTransaction fest.<br /><br /> Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert. Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.<br /><br /> Wenn Sie die Firewall nach der Konfiguration von WS-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben. Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS-AT ohne zusätzliche Eingabe ausgeführt.|  
|-Timeout: \<sek. >|Gibt das Standardtimeout in Sekunden an. Gültige Werte reichen von 1 bis 3600.|  
|-traceActivity: \<enable&#124;deaktivieren >|Aktiviert oder deaktiviert die Ablaufverfolgung von Aktivitätsereignissen.|  
|-TraceLevel: \<off&#124;Fehler&#124;kritische&#124;Warnung&#124;Informationen&#124; ausführlich&#124;alle >}|Gibt die Ablaufverfolgungsebene an.|  
|-tracePII: \<enable&#124;deaktivieren >|Aktiviert oder deaktiviert die Ablaufverfolgung von persönlich identifizierbaren Informationen.|  
|-TraceProp: \<enable&#124;deaktivieren >|Aktiviert oder deaktiviert die Ablaufverfolgung von Propagierungsereignissen.|  
|-restart|Startet MSDTC neu, um Änderungen sofort zu aktivieren. Wenn dies nicht angegeben wird, werden die Änderungen erst wirksam, wenn MSDTC neu gestartet wird.|  
|-show|Zeigt die aktuellen WS-AtomicTransaction-Protokolleinstellungen an.|  
|-virtualserver: \<virtualserver >|Gibt den DTC-Ressourcenclusternamen an.|  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von WS-AtomicTransaction](./feature-details/using-ws-atomictransaction.md)
- [Konfigurieren der Unterstützung von WS-Atomic-Transaction](./feature-details/configuring-ws-atomic-transaction-support.md)
