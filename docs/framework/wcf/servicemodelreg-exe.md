---
title: ServiceModel Registration-Tool (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: a6f65ccc6caa0a7e496e7de8c83259ab48903753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183105"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>ServiceModel Registration-Tool (ServiceModelReg.exe)
Dieses Befehlszeilentool bietet die Möglichkeit, die Registrierung von WCF- und WF-Komponenten auf einem einzelnen Computer zu verwalten. Unter normalen Umständen müssen Sie dieses Tool nicht verwenden, da WCF- und WF-Komponenten bei der Installation konfiguriert werden. Wenn jedoch bei der Dienstaktivierung Probleme auftreten, können Sie versuchen, die Komponenten mithilfe dieses Tools zu registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Das Tool befindet sich an folgendem Speicherort:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
> Wenn das ServiceModel-Registrierungstool unter Windows Vista ausgeführt wird, spiegelt das Dialogfeld **Windows-Features** möglicherweise nicht wider, dass die **HTTP-Aktivierungsoption** von Windows Communication Foundation unter **Microsoft .NET Framework 3.0** aktiviert ist. Auf das Dialogfeld **Windows-Features** kann zugegriffen werden, indem Sie auf **Start**klicken, dann auf **Ausführen** klicken und dann **OptionalFeatures**eingeben.  
  
 Die folgenden Tabellen beschreiben die Optionen, die mit ServiceModelReg.exe verwendet werden können.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`-ia`|Installiert alle WCF- und WF-Komponenten.|  
|`-ua`|Deinstalliert alle WCF- und WF-Komponenten.|  
|`-r`|Repariert alle WCF- und WF-Komponenten.|  
|`-i`|Installiert mit -c angegebene WCF- und WF-Komponenten.|  
|`-u`|Deinstalliert mit -c angegebene WCF- und WF-Komponenten.|  
|`-c`|Installiert oder deinstalliert eine Komponente:<br /><br /> - httpnamespace – HTTP-Namespace-Reservierung<br />- tcpportsharing – TCP-Port-Sharing-Dienst<br />- tcpactivation – TCP-Aktivierungsdienst (nicht unterstützt auf .NET 4 Client Profil)<br />- namedpipeactivation – Named Pipe-Aktivierungsdienst (nicht unterstützt im .NET 4-Clientprofil<br />- msmqactivation – MSMQ-Aktivierungsdienst (nicht unterstützt im .NET 4-Clientprofil<br />- etw – ETW-Ereignisablaufverfolgungsmanifeste (Windows Vista oder höher)|  
|`-q`|Stiller Modus (nur Protokollierung von Anzeigefehlern)|  
|`-v`|Ausführlicher Modus.|  
|`-nologo`|Die Copyright- und Bannermeldung werden unterdrückt.|  
|`-?`|Zeigt Hilfetext an.|  
  
## <a name="fixing-the-fileloadexception-error"></a>Beheben des FileLoadException-Fehlers  
 Wenn Sie frühere Versionen von WCF auf Ihrem `FileLoadFoundException` Computer installiert haben, wird möglicherweise eine Fehlermeldung angezeigt, wenn Sie das ServiceModelReg-Tool ausführen, um eine neue Installation zu registrieren. Dies kann auch auftreten, wenn Sie Dateien von der vorherigen Installation manuell entfernt haben, aber die machine.config-Einstellungen unverändert gelassen haben.  
  
 Die Fehlermeldung lautet ungefähr folgendermaßen:  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Die Meldung sollte angeben, dass die System.ServiceModel Version&#160;2.0.0.0-Assembly mit einem frühen CTP (Customer Technology Preview)-Release installiert wurde. Die aktuelle Version der System.ServiceModel-Assembly lautet jedoch 3.0.0.0. Daher tritt dieses Problem auf, wenn Sie die offizielle WCF-Version auf einem Computer installieren möchten, auf dem eine frühe CTP-Version von WCF installiert, aber nicht vollständig deinstalliert wurde.  
  
 ServiceModelReg.exe kann keine vorherigen Versionseinträge bereinigen und die Einträge der neuen Version nicht registrieren. Die einzige Problemumgehung besteht darin, machine.config manuell zu bearbeiten. Sie können diese Datei an folgendem Speicherort finden.  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 Wenn Sie WCF auf einem 64-Bit-Computer ausführen, sollten Sie dieselbe Datei auch an diesem Speicherort bearbeiten.  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 Suchen Sie alle XML-Knoten in dieser Datei, die auf "System.ServiceModel, Version=2.0.0.0" verweisen, löschen Sie sie und alle untergeordneten Knoten. Speichern Sie die Datei, und führen Sie ServiceModelReg.exe erneut aus, um dieses Problem zu beheben.  
  
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
