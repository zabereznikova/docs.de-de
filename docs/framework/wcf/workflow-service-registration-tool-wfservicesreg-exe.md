---
title: Registrierungstool für Workflowdienste (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 5e7d39062a8ad016eebf949daa625a5ba7848328
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921233"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a>Registrierungstool für Workflowdienste (WFServicesReg.exe)
Beim Registrierungstool für Workflow Services (WFServicesReg.exe) handelt es sich um ein eigenständiges Tool zum Hinzufügen, Entfernen oder Reparieren der Konfigurationselemente für Windows Workflow Foundation (WF)-Dienste.  
  
## <a name="syntax"></a>Syntax  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Tool befindet sich an der .NET Framework 3,5-Installation, insbesondere%windir%\Microsoft.NET\Framework\v3.5, oder unter%windir%\Microsoft.NET\framework64\v3.5 auf 64-Bit-Computern.  
  
 In den folgenden Tabellen werden die Optionen beschrieben, die mit dem Registrierungstool für Workflow Services (WFServicesReg.exe) verwendet werden können.  
  
|-Option|Beschreibung|  
|------------|-----------------|  
|`/c`|Dient zum Konfigurieren von Windows Workflow Services. Wird zum Installieren und Reparieren verwendet.|  
|`/r`|Entfernt die Konfiguration von Windows Workflow Services.|  
|`/v`|Druckt ausführliche Informationen (entweder für die Konfiguration oder für das Löschen).|  
|`/m`|Aktiviert das MSI-Protokollierungsformat.|  
|`/i`|Minimiert das Fenster, wenn die Anwendung ausgeführt wird.|  
  
## <a name="registration"></a>Registrierung  
 Die Datei Web.config wird untersucht. Dabei wird Folgendes registriert:  
  
- .NET Framework 3,5 Verweisassemblys.  
  
- Ein Buildanbieter für XOML-Dateien.  
  
- HTTP-Handler für XOML- und RULES-Dateien.  
  
 Die Datei Machine.config wird untersucht. Dabei werden die folgenden Erweiterungen registriert:  
  
- behaviorExtensions  
  
- bindingElementExtensions  
  
- bindingExtensions  
  
 Des Weiteren werden die folgenden Importprogramme für Clientmetadaten registriert:  
  
- policyImporters  
  
- wsdlImporters  
  
 Auch XOML und RULES-Skriptzuordnungen und -Handler werden in der IIS-Metabasis registriert.  
  
 Auf Computern unter Windows Server 2003 und Windows XP (IIS 5,1 und IIS 6,0) werden ein Satz von XOML-und Rules-Skript Zuordnungen registriert.  
  
 Auf 64-Bit-Computern werden bei aktiviertem `Enable32BitAppOnWin64`-Schalter WOW-Modus-Skriptzuordnungen registriert, bei aktiviertem `Enable32BitAppOnWin64`-Schalter werden systemeigene 64-Bit-Skriptzuordnungen registriert.  
  
 Auf Computern unter Windows Vista und Windows Server 2008 (IIS 7,0 und höher) werden zwei Sätze von XOML-und Rules-Handlern registriert: eine für den integrierten Modus und eine für den klassischen Modus.  
  
 Auf 64-Bit-Computern werden drei Handlersätze registriert (unabhängig vom Zustand des `Enable32BitAppOnWin64`-Schalters): einer für den integrierten Modus, einer für den klassischen WOW-Modus und einer für den systemeigenen klassischen 64-Bit-Modus.  
  
> [!NOTE]
> Im Gegensatz zu ServiceModelreg.exe ist es bei WFServicesReg.exe nicht zulässig, Skriptzuordnungen oder Handler für eine bestimmte Website hinzuzufügen, zu entfernen oder zu reparieren. Eine Möglichkeit zum Umgehen dieses Problems finden Sie im Abschnitt "Reparieren der Skriptzuordnungen".  
  
## <a name="usage-scenarios"></a>Verwendungsszenarien  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a>Installieren von IIS, nachdem .NET Framework&#160;3.5 installiert wurde  
 Auf einem Windows Server 2003-Computer wird .NET Framework 3,5 vor der IIS-Installation installiert. Da die IIS-Metabasis nicht verfügbar ist, ist die Installation von .NET Framework 3,5 erfolgreich, ohne dass XOML-und Rules-Skript Zuordnungen installiert werden.  
  
 Verwenden Sie nach der Installation von IIS das Tool WFServicesReg.exe mit dem `/c`-Schalter, um diese Skriptzuordnungen zu installieren.  
  
### <a name="repairing-the-scriptmaps"></a>Reparieren der Skriptzuordnungen  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a>Gelöschte Skriptzuordnung des Knotens "Websites"  
 Auf einem Windows Server 2003-Computer werden XOML-oder-Rules-Regeln versehentlich aus dem Website Knoten gelöscht. Dies lässt sich durch Ausführen des Tools WFServicesReg.exe mit dem `/c`-Schalter reparieren.  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a>Gelöschte Skriptzuordnung einer bestimmten Website  
 Auf einem Windows Server 2003-Computer werden XOML-oder. Rules-Regeln versehentlich von einer bestimmten Website (z. b. der Standard Website) und nicht vom Website Knoten gelöscht.  
  
 Zum Reparieren von gelöschten Handlern für eine bestimmte Website sollten Sie "WFServicesReg. exe/r" ausführen, um Handler von allen Websites zu entfernen. führen Sie dann "WFServicesReg. exe/c" aus, um die entsprechenden Handler für alle Websites zu erstellen.  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a>Konfigurieren von Handlern nach Wechseln des IIS-Modus  
 Wenn sich IIS im freigegebenen Konfigurations Modus befindet und .NET Framework 3,5 installiert ist, wird die IIS-Metabase unter einem freigegebenen Speicherort konfiguriert. Wird für IIS zum nicht freigegebenen Konfigurationsmodus gewechselt, sind die erforderlichen Handler nicht in der lokalen Metabasis vorhanden. Zum ordnungsgemäßen Konfigurieren der lokalen Metabase können Sie entweder die freigegebene Metabase in eine lokale Version importieren oder "WFServicesReg. exe/c" ausführen, um die lokale Metabase zu konfigurieren.
