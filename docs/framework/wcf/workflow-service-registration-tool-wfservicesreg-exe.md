---
title: Registrierungstool für Workflow Services (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: bb0989fb8747a5065ce3d7332311cdefba95b80d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425286"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a>Registrierungstool für Workflow Services (WFServicesReg.exe)
Beim Registrierungstool für Workflow Services (WFServicesReg.exe) handelt es sich um ein eigenständiges Tool zum Hinzufügen, Entfernen oder Reparieren der Konfigurationselemente für Windows Workflow Foundation (WF)-Dienste.  
  
## <a name="syntax"></a>Syntax  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Tool befindet sich im Installationsverzeichnis von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Ausführlicher Pfad: %windir%\Microsoft.NET\Framework\v3.5 oder (auf 64-Bit-Computern) unter %windir%\Microsoft.NET\Framework64\v3.5.  
  
 In den folgenden Tabellen werden die Optionen beschrieben, die mit dem Registrierungstool für Workflow Services (WFServicesReg.exe) verwendet werden können.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/c`|Dient zum Konfigurieren von Windows Workflow Services. Wird zum Installieren und Reparieren verwendet.|  
|`/r`|Entfernt die Konfiguration von Windows Workflow Services.|  
|`/v`|Druckt ausführliche Informationen (entweder für die Konfiguration oder für das Löschen).|  
|`/m`|Aktiviert das MSI-Protokollierungsformat.|  
|`/i`|Minimiert das Fenster, wenn die Anwendung ausgeführt wird.|  
  
## <a name="registration"></a>Registrierung  
 Die Datei Web.config wird untersucht. Dabei wird Folgendes registriert:  
  
- [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Referenzassemblys  
  
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
  
 Auf [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]-und [!INCLUDE[wxp](../../../includes/wxp-md.md)] Computern (IIS 5,1 und IIS 6,0) werden ein Satz von XOML-und Rules-Skript Zuordnungen registriert.  
  
 Auf 64-Bit-Computern werden bei aktiviertem `Enable32BitAppOnWin64`-Schalter WOW-Modus-Skriptzuordnungen registriert, bei aktiviertem `Enable32BitAppOnWin64`-Schalter werden systemeigene 64-Bit-Skriptzuordnungen registriert.  
  
 Auf [!INCLUDE[wv](../../../includes/wv-md.md)]-und Windows Server 2008-Computern (IIS 7,0 und höher) werden zwei Sätze von XOML-und Rules-Handlern registriert: eine für den integrierten Modus und eine für den klassischen Modus.  
  
 Auf 64-Bit-Computern werden drei Handlersätze registriert (unabhängig vom Zustand des `Enable32BitAppOnWin64`-Schalters): einer für den integrierten Modus, einer für den klassischen WOW-Modus und einer für den systemeigenen klassischen 64-Bit-Modus.  
  
> [!NOTE]
> Im Gegensatz zu ServiceModelreg.exe ist es bei WFServicesReg.exe nicht zulässig, Skriptzuordnungen oder Handler für eine bestimmte Website hinzuzufügen, zu entfernen oder zu reparieren. Eine Möglichkeit zum Umgehen dieses Problems finden Sie im Abschnitt "Reparieren der Skriptzuordnungen".  
  
## <a name="usage-scenarios"></a>Verwendungsszenarien  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a>Installieren von IIS, nachdem .NET Framework&#160;3.5 installiert wurde  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] vor IIS installiert. Da die IIS-Metabasis nicht verfügbar ist, ist die Installation von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] ohne Installation von XOML- und RULES-Skriptzuordnungen erfolgreich.  
  
 Verwenden Sie nach der Installation von IIS das Tool WFServicesReg.exe mit dem `/c`-Schalter, um diese Skriptzuordnungen zu installieren.  
  
### <a name="repairing-the-scriptmaps"></a>Reparieren der Skriptzuordnungen  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a>Gelöschte Skriptzuordnung des Knotens "Websites"  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES versehentlich aus dem Websites-Knoten gelöscht. Dies lässt sich durch Ausführen des Tools WFServicesReg.exe mit dem `/c`-Schalter reparieren.  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a>Gelöschte Skriptzuordnung einer bestimmten Website  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES nicht aus dem Websites-Knoten, sondern versehentlich aus einer bestimmten Website (beispielsweise der Standardwebsite) gelöscht.  
  
 Zum Reparieren von gelöschten Handlern für eine bestimmte Website sollten Sie "WFServicesReg. exe/r" ausführen, um Handler von allen Websites zu entfernen. führen Sie dann "WFServicesReg. exe/c" aus, um die entsprechenden Handler für alle Websites zu erstellen.  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a>Konfigurieren von Handlern nach Wechseln des IIS-Modus  
 Befindet sich IIS im freigegebenen Konfigurationsmodus und ist [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert, wird die IIS-Metabasis an einem freigegebenen Speicherort konfiguriert. Wird für IIS zum nicht freigegebenen Konfigurationsmodus gewechselt, sind die erforderlichen Handler nicht in der lokalen Metabasis vorhanden. Zum ordnungsgemäßen Konfigurieren der lokalen Metabase können Sie entweder die freigegebene Metabase in eine lokale Version importieren oder "WFServicesReg. exe/c" ausführen, um die lokale Metabase zu konfigurieren.
