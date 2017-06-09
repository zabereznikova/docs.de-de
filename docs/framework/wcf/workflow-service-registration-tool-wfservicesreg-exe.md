---
title: "Registrierungstool f&#252;r Workflow Services (WFServicesReg.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Registrierungstool f&#252;r Workflow Services (WFServicesReg.exe)
Beim Registrierungstool für Workflow Services \(WFServicesReg.exe\) handelt es sich um ein eigenständiges Tool zum Hinzufügen, Entfernen oder Reparieren der Konfigurationselemente für Windows Workflow Foundation \(WF\)\-Dienste.  
  
## Syntax  
  
```  
  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## Hinweise  
 Das Tool befindet sich im Installationsverzeichnis von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Ausführlicher Pfad: %windir%\\Microsoft.NET\\Framework\\v3.5 oder \(auf 64\-Bit\-Computern\) unter %windir%\\Microsoft.NET\\Framework64\\v3.5.  
  
 In den folgenden Tabellen werden die Optionen beschrieben, die mit dem Registrierungstool für Workflow Services \(WFServicesReg.exe\) verwendet werden können.  
  
|Option|Beschreibung|  
|------------|------------------|  
|`/c`|Dient zum Konfigurieren von Windows Workflow Services.Wird zum Installieren und Reparieren verwendet.|  
|`/r`|Entfernt die Konfiguration von Windows Workflow Services.|  
|`/v`|Druckt ausführliche Informationen \(entweder für die Konfiguration oder für das Löschen\).|  
|`/m`|Aktiviert das MSI\-Protokollierungsformat.|  
|`/i`|Minimiert das Fenster, wenn die Anwendung ausgeführt wird.|  
  
## Registrierung  
 Die Datei Web.config wird untersucht. Dabei wird Folgendes registriert:  
  
-   [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]\-Referenzassemblys  
  
-   Ein Buildanbieter für XOML\-Dateien.  
  
-   HTTP\-Handler für XOML\- und RULES\-Dateien.  
  
 Die Datei Machine.config wird untersucht. Dabei werden die folgenden Erweiterungen registriert:  
  
-   behaviorExtensions  
  
-   bindingElementExtensions  
  
-   bindingExtensions  
  
 Des Weiteren werden die folgenden Importprogramme für Clientmetadaten registriert:  
  
-   policyImporters  
  
-   wsdlImporters  
  
 Auch XOML und RULES\-Skriptzuordnungen und \-Handler werden in der IIS\-Metabasis registriert.  
  
 Auf Computern unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../includes/wxp-md.md)] \(IIS 5.1 oder [!INCLUDE[iis601](../../../includes/iis601-md.md)]\) wird ein XOML\- und RULES\-Skriptzuordnungssatz registriert.  
  
 Auf 64\-Bit\-Computern werden bei aktiviertem `Enable32BitAppOnWin64`\-Schalter WOW\-Modus\-Skriptzuordnungen registriert, bei aktiviertem `Enable32BitAppOnWin64`\-Schalter werden systemeigene 64\-Bit\-Skriptzuordnungen registriert.  
  
 Auf Computern unter [!INCLUDE[wv](../../../includes/wv-md.md)] oder Windows Server 2008 \(IIS 7.0 oder höher\) werden zwei XOML\- und RULES\-Handlersätze registriert: einer für den integrierten und einer für den klassischen Modus.  
  
 Auf 64\-Bit\-Computern werden drei Handlersätze registriert \(unabhängig vom Zustand des `Enable32BitAppOnWin64`\-Schalters\): einer für den integrierten Modus, einer für den klassischen WOW\-Modus und einer für den systemeigenen klassischen 64\-Bit\-Modus.  
  
> [!NOTE]
>  Im Gegensatz zu ServiceModelreg.exe ist es bei WFServicesReg.exe nicht zulässig, Skriptzuordnungen oder Handler für eine bestimmte Website hinzuzufügen, zu entfernen oder zu reparieren.Eine Möglichkeit zum Umgehen dieses Problems finden Sie im Abschnitt "Reparieren der Skriptzuordnungen".  
  
## Verwendungsszenarien  
  
### Installieren von IIS, nachdem .NET Framework 3.5 installiert wurde  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] vor IIS installiert.Da die IIS\-Metabasis nicht verfügbar ist, ist die Installation von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] ohne Installation von XOML\- und RULES\-Skriptzuordnungen erfolgreich.  
  
 Verwenden Sie nach der Installation von IIS das Tool WFServicesReg.exe mit dem `/c`\-Schalter, um diese Skriptzuordnungen zu installieren.  
  
### Reparieren der Skriptzuordnungen  
  
#### Gelöschte Skriptzuordnung des Knotens "Websites"  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES versehentlich aus dem Websites\-Knoten gelöscht.Dies lässt sich durch Ausführen des Tools WFServicesReg.exe mit dem `/c`\-Schalter reparieren.  
  
#### Gelöschte Skriptzuordnung einer bestimmten Website  
 Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES nicht aus dem Websites\-Knoten, sondern versehentlich aus einer bestimmten Website \(beispielsweise der Standardwebsite\) gelöscht.  
  
 Führen Sie zum Reparieren der gelöschten Handler einer bestimmten Website den Befehl "WFServicesReg.exe \/r" aus, um die Handler aller Websites zu entfernen, und führen Sie anschließend "WFServicesReg.exe \/c" aus, um für alle Websites die entsprechenden Handler zu erstellen.  
  
### Konfigurieren von Handlern nach Wechseln des IIS\-Modus  
 Befindet sich IIS im freigegebenen Konfigurationsmodus und ist [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert, wird die IIS\-Metabasis an einem freigegebenen Speicherort konfiguriert.Wird für IIS zum nicht freigegebenen Konfigurationsmodus gewechselt, sind die erforderlichen Handler nicht in der lokalen Metabasis vorhanden.Zum ordnungsgemäßen Konfigurieren der Metabasis können Sie entweder die freigegebene Metabasis lokal importieren oder den Befehl "WFServicesReg.exe \/c" ausführen, um die lokale Metabasis zu konfigurieren.