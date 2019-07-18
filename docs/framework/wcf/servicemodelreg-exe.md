---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 5fab1a356cd035ed006bfe90d713e179907e0137
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051779"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>ServiceModel Registration-Tool (ServiceModelReg.exe)
Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten. Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden. Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Tool befindet sich an folgendem Speicherort:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
>  Wenn die ServiceModel-Registrierungstool ausgeführt wird [!INCLUDE[wv](../../../includes/wv-md.md)], **Windows Features** Dialogfeld u. u. nicht wiedergegeben, die die **Windows Communication Foundation-HTTP-Aktivierung** Option **Microsoft .NET Framework 3.0** aktiviert ist. Die **Windows Features** Dialogfeld zugegriffen werden kann, indem Sie auf **starten**, klicken Sie dann auf **ausführen** und geben dann **OptionalFeatures**.  
  
 Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`-ia`|Installiert alle WCF- und WF-Komponenten.|  
|`-ua`|Deinstalliert alle WCF- und WF-Komponenten.|  
|`-r`|Repariert alle WCF- und WF-Komponenten.|  
|`-i`|Installiert mit -c angegebene WCF- und WF-Komponenten.|  
|`-u`|Deinstalliert mit -c angegebene WCF- und WF-Komponenten.|  
|`-c`|Installiert oder deinstalliert eine Komponente:<br /><br /> -Httpnamespace – HTTP-Namespace-Reservierung<br />-Tcpportsharing – TCP-Portfreigabedienst<br />-Tcpactivation – TCP-Aktivierungsdienst (die für .NET 4 Client Profile nicht unterstützt)<br />-Namedpipeactivation – Named Pipe Activation Service (für .NET 4 Client Profile nicht unterstützt<br />-der Msmqactivation – MSMQ-Aktivierungsdienst (für .NET 4 Client Profile nicht unterstützt<br />-Etw-ETW-ereignisablaufverfolgungsmanifeste (Windows Vista oder höher)|  
|`-q`|Stiller Modus (nur Protokollierung von Anzeigefehlern)|  
|`-v`|Ausführlicher Modus.|  
|`-nologo`|Die Copyright- und Bannermeldung werden unterdrückt.|  
|`-?`|Zeigt Hilfetext an.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Beheben des FileLoadException-Fehlers  
 Wenn Sie frühere Versionen von WCF auf Ihrem Computer installiert haben, erhalten Sie eventuell eine `FileLoadFoundException` Fehler, wenn Sie das ServiceModelReg-Tool zum Registrieren einer neuen Installations ausführen. Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.  
  
 Die Fehlermeldung lautet ungefähr folgendermaßen:  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Die Meldung sollte angeben, dass die System.ServiceModel Version&amp;#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde. Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0. Aus diesem Grund dieses Problem tritt auf, wenn Sie der offiziellen Veröffentlichung von WCF auf einem Computer zu installieren, in eine frühere CTP-Version von WCF installiert wurde, aber nicht vollständig deinstalliert wurde, möchten.  
  
 ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren. Die einzige Problemumgehung ist die manuelle Bearbeitung von machine.config. Sie finden diese Datei am folgenden Speicherort.  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie auch die gleiche Datei an diesem Speicherort bearbeiten.  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 Suchen von XML-Knoten in dieser Datei, die auf "System.ServiceModel, Version = 2.0.0.0", löschen Sie diese und alle untergeordneten Knoten. Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.  
  
## <a name="examples"></a>Beispiele  
 In den folgenden Beispielen wird gezeigt, wie die häufigsten Optionen des Tools ServiceModelReg.exe verwendet werden.  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
