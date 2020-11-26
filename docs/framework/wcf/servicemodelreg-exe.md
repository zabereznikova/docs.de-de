---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
description: Verwenden Sie dieses Befehlszeilen Tool, um die Registrierung von WCF-und WF-Komponenten auf einem einzelnen Computer zu verwalten, wenn Probleme bei der Dienst Aktivierung auftreten.
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: d8d5bc4dc3de021e2110fb953dbc4d6c7d7972d0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235921"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>ServiceModel Registration-Tool (ServiceModelReg.exe)

Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten. Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden. Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Hinweise  

 Das Tool befindet sich an folgendem Speicherort:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
> Wenn das Service Model-Registrierungs Tool unter Windows Vista ausgeführt wird, zeigt das Dialogfeld **Windows-Features** möglicherweise nicht an, dass die **Windows Communication Foundation http-Aktivierungs** Option unter **Microsoft .NET Framework 3,0** aktiviert ist. Sie können auf das Dialogfeld " **Windows-Features** " zugreifen, indem Sie auf **Start** und dann auf **Ausführen** klicken und dann **OptionalFeatures** eingeben.  
  
 Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|`-ia`|Installiert alle WCF- und WF-Komponenten.|  
|`-ua`|Deinstalliert alle WCF- und WF-Komponenten.|  
|`-r`|Repariert alle WCF- und WF-Komponenten.|  
|`-i`|Installiert mit -c angegebene WCF- und WF-Komponenten.|  
|`-u`|Deinstalliert mit -c angegebene WCF- und WF-Komponenten.|  
|`-c`|Installiert oder deinstalliert eine Komponente:<br /><br /> -httpnamespace – HTTP-Namespace Reservierung<br />-tcpportsharing – TCP-Port Freigabe Dienst<br />-tcpactivations – TCP-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)<br />-namedpipeactivations – Named Pipe-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)<br />-der MsmqActivation – MSMQ-Aktivierungs Dienst (für .NET 4 Client Profile nicht unterstützt)<br />-etw – ETW-Ereignis Ablauf Verfolgungs Manifeste (Windows Vista oder höher)|  
|`-q`|Stiller Modus (nur Protokollierung von Anzeigefehlern)|  
|`-v`|Ausführlicher Modus.|  
|`-nologo`|Die Copyright- und Bannermeldung werden unterdrückt.|  
|`-?`|Zeigt Hilfetext an.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Beheben des FileLoadException-Fehlers  

 Wenn Sie frühere Versionen von WCF auf dem Computer installiert haben, erhalten Sie möglicherweise einen `FileLoadFoundException` Fehler, wenn Sie das Service Model reg-Tool ausführen, um eine neue Installation zu registrieren. Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.  
  
 Die Fehlermeldung lautet ungefähr folgendermaßen:  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Die Meldung sollte angeben, dass die System.ServiceModel Version&#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde. Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0. Dieses Problem ist daher aufgetreten, wenn Sie die offizielle WCF-Version auf einem Computer installieren möchten, auf dem eine frühe CTP-Version von WCF installiert, aber nicht vollständig deinstalliert wurde.  
  
 ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren. Die einzige Problem Umgehung besteht darin, machine.config manuell zu bearbeiten. Sie finden diese Datei am folgenden Speicherort.  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie auch dieselbe Datei an diesem Speicherort bearbeiten.  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 Suchen Sie alle XML-Knoten in dieser Datei, die auf "System. Service Model, Version = 2.0.0.0" verweisen, löschen Sie Sie und alle untergeordneten Knoten. Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.  
  
## <a name="examples"></a>Beispiele  

 In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
