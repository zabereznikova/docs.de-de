---
title: "WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)
Das WS\-AtomicTransaction\-Konfigurationsdienstprogramm wird zur Konfiguration von grundlegenden WS\-AtomicTransaction\-Unterstützungseinstellungen verwendet.  
  
## Syntax  
  
```  
  
wsatConfig [Options]  
```  
  
## Hinweise  
 Dieses Befehlszeilentool kann nur dazu verwendet werden, grundlegende WS\-AT\-Einstellungen auf einem lokalen Computer zu konfigurieren.Wenn Sie die Konfiguration sowohl auf lokalen als auch auf Remotecomputern vornehmen möchten, sollten Sie das MMC\-Snap\-In verwenden, wie unter [Konfigurieren der WS\-AtomicTransaction\-Unterstützung](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md) beschrieben.  
  
 Das Befehlszeilentool befindet sich im Windows SDK\-Installationspfad:  
  
 %SystemRoot%\\Microsoft.Net\\Framework\\v3.0\\Windows Communication Foundation\\wsatConfig.exe  
  
 Wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ausführen, müssen Sie vor dem Ausführen von WsatConfig.exe ein Update herunterladen.Weitere Informationen zu diesem Update finden Sie unter [Update für Commerce Server 2007 \(KB912817\)](http://go.microsoft.com/fwlink/?LinkId=95340) und [Verfügbarkeit von Windows XP COM\+ Hotfix Rollup Package 13](http://go.microsoft.com/fwlink/?LinkId=95341) \(möglicherweise in englischer Sprache\).  
  
 In der folgenden Tabelle werden die Optionen angezeigt, die mit dem WS\-AtomicTransaction\-Konfigurationsdienstprogramm \(wsatConfig.exe\) verwendet werden können.  
  
> [!NOTE]
>  Wenn Sie ein SSL\-Zertifikat für einen bestimmten Anschluss festlegen, wird dabei das ursprüngliche SSL\-Zertifikat überschrieben, das diesem Anschluss zugeordnet ist \(sofern vorhanden\).  
  
|Optionen|Beschreibung|  
|--------------|------------------|  
|\-accounts:\<account,\>|Gibt eine durch Trennzeichen getrennte Liste von Konten an, die von WS\-AtomicTransaction verwendet werden können.Die Gültigkeit dieser Konten wird nicht überprüft.|  
|\-accountsCerts:\<thumb\>&#124;"Issuer\\SubjectName",\>|Gibt eine durch Trennzeichen getrennte Liste von Zertifikaten an, die von WS\-AtomicTransaction verwendet werden können.Die Zertifikate werden vom Fingerabdruck oder vom Issuer\\SubjectName\-Paar angegeben.Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|\-endpointCert:\<machine&#124;\<thumb\>&#124;"Issuer\\SubjectName"\>|Verwendet das Computerzertifikat oder ein anderes lokales Endpunktzertifikat, das vom Fingerabdruck oder Issuer\\SubjectName\-Paar angegeben wird.Verwendet {EMPTY} für den Betreffnamen, wenn dieser leer ist.|  
|\-maxTimeout:\<sec\>|Gibt das maximale Timeout in Sekunden an.Gültige Werte reichen von 0 bis 3600.|  
|\-network:\<enable&#124;disable\>|Aktiviert oder deaktiviert die WS\-AtomicTransaction\-Netzwerkunterstützung.|  
|\-port:\<portNum\>|Legt den HTTPS\-Anschluss für WS\-AtomicTransaction fest.<br /><br /> Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert.Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.<br /><br /> Wenn Sie die Firewall nach der Konfiguration von WS\-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben.Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS\-AT ohne zusätzliche Eingabe ausgeführt.|  
|\-timeout:\<sec\>|Gibt das Standardtimeout in Sekunden an.Gültige Werte reichen von 1 bis 3600.|  
|\-traceActivity:\<enable&#124;disable\>|Aktiviert oder deaktiviert die Ablaufverfolgung von Aktivitätsereignissen.|  
|\-traceLevel:\<Off&#124;Error&#124;Critical&#124;Warning&#124;Information&#124; Verbose&#124;All\>}|Gibt die Ablaufverfolgungsebene an.|  
|\-tracePII:\<enable&#124;disable\>|Aktiviert oder deaktiviert die Ablaufverfolgung von persönlich identifizierbaren Informationen.|  
|\-traceProp:\<enable&#124;disable\>|Aktiviert oder deaktiviert die Ablaufverfolgung von Propagierungsereignissen.|  
|\-restart|Startet MSDTC neu, um Änderungen sofort zu aktivieren.Wenn dies nicht angegeben wird, werden die Änderungen erst wirksam, wenn MSDTC neu gestartet wird.|  
|\-show|Zeigt die aktuellen WS\-AtomicTransaction\-Protokolleinstellungen an.|  
|\-virtualServer:\<virtualServer\>|Gibt den DTC\-Ressourcenclusternamen an.|  
  
## Siehe auch  
 [Verwenden von WS\-AtomicTransaction](../../../docs/framework/wcf/feature-details/using-ws-atomictransaction.md)   
 [Konfigurieren der WS\-AtomicTransaction\-Unterstützung](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)