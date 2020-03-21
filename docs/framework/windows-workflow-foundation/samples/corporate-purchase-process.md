---
title: Unternehmenseinkaufsprozess
ms.date: 03/30/2017
ms.assetid: a5e57336-4290-41ea-936d-435593d97055
ms.openlocfilehash: 93cfc3546fc312f046c4a5e1dd63dfb357f143c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182873"
---
# <a name="corporate-purchase-process"></a>Unternehmenseinkaufsprozess
In diesem Beispiel wird die Erstellung eines einfachen, auf Ausschreibungen basierenden Einkaufsvorgangs veranschaulicht, bei dem automatisch das beste Angebot ausgewählt wird. In diesem Beispiel werden <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601> und <xref:System.Activities.Statements.ForEach%601> sowie eine benutzerdefinierte Aktivität kombiniert, um einen Workflow zu erstellen, der diesen Vorgang darstellt.

 Dieses Beispiel enthält eine ASP.NET Clientanwendung, die die Interaktion mit dem Prozess als verschiedene Teilnehmer (als ursprünglicher Anforderer oder ein bestimmter Kreditor) ermöglicht.

## <a name="requirements"></a>Requirements (Anforderungen)

- Visual Studio 2012.

- [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].

## <a name="demonstrates"></a>Zeigt

- Benutzerdefinierte Aktivitäten

- Komposition von Aktivitäten

- Lesezeichen.

- Dauerhaftigkeit

- Schematisierte Dauerhaftigkeit

- Ablaufverfolgung

- Nachverfolgung

- Hosting [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in verschiedenen Clients (ASP.NET Webanwendungen und WinForms-Anwendungen).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\PurchaseProcess`  
  
## <a name="description-of-the-process"></a>Beschreibung des Vorgangs  
 Dieses Beispiel zeigt eine Implementierung eines Windows Workflow Foundation (WF)-Programms, um Vorschläge von Anbietern für ein generisches Unternehmen zu sammeln.  
  
1. Ein Mitarbeiter des Unternehmens X erstellt eine Ausschreibung (Request for Proposal, RFP).  
  
    1. Der Mitarbeiter gibt den Titel und die Beschreibung für die Ausschreibung ein.  
  
    2. Der Mitarbeiter wählt die Kreditoren aus, die zum Einreichen von Vorschlägen eingeladen werden sollen.  
  
2. Der Mitarbeiter versendet die Ausschreibung.  
  
    1. Eine Instanz des Workflows wird erstellt.  
  
    2. Der Workflow wartet darauf, dass alle Anbieter ihre Angebote einreichen.  
  
3. Nachdem alle Angebote empfangen wurden, durchläuft der Workflow alle eingegangenen Angebote und wählt das beste aus.  
  
    1. Jeder Anbieter hat einen Ruf (in diesem Beispiel wird die Reputationliste in VendorRepository.cs gespeichert).  
  
    2. Der Gesamtwert des Angebots wird ermittelt, indem der vom Anbieter eingegebene Wert mit dem aufgezeichneten Ruf des Anbieters multipliziert und durch 100 dividiert wird: (vom Anbieter eingegebener Wert) * (gespeicherte Reputation des Anbieters)/100.  
  
4. Der ursprüngliche Anforderer kann alle eingesendeten Angebote anzeigen. Das beste Angebot wird in einem speziellen Abschnitt des Berichts präsentiert.  
  
## <a name="process-definition"></a>Prozessdefinition  
 Die Kernlogik des Beispiels verwendet eine <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität, die auf die Angebote der einzelnen Anbieter wartet (wobei eine benutzerdefinierte Aktivität, die ein Lesezeichen erstellt, verwendet wird) und das Angebot des Anbieters als RFP registriert (wobei eine <xref:System.Activities.Statements.InvokeMethod>-Aktivität verwendet wird).  
  
 Im Beispiel werden dann alle eingegangenen, im `RfpRepository` gespeicherten Angebote durchlaufen, wobei der angepasste Wert (mithilfe einer <xref:System.Activities.Statements.Assign>-Aktivität und von <xref:System.Activities.Expressions>-Aktivitäten) berechnet wird. Wenn der angepasste Wert besser als das zuvor als bestes Angebot eingestufte Angebot ist, wird der neue Wert als bestes Angebot (mithilfe der <xref:System.Activities.Statements.If>-Aktivität und <xref:System.Activities.Statements.Assign>-Aktivität) zugeordnet.  
  
## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel  
 Dieses Beispiel enthält die folgenden Projekte.  
  
|Project|Beschreibung|  
|-------------|-----------------|  
|Allgemein|Die im Vorgang verwendeten Entitätsobjekte (Ausschreibung, Anbieter und Angebot).|  
|WfDefinition|Die Definition des Vorgangs (als [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Programm) und der Host (`PurchaseProcessHost`), die von den Clientanwendungen zum Erstellen und Verwenden von Instanzen des Einkaufsworkflows verwendet werden.|  
|WebClient|Eine ASP.NET Clientanwendung, mit der die Benutzer Instanzen des Kaufprozesses erstellen und daran teilnehmen können. Sie verwendet einen benutzerdefinierten Host für die Interaktion mit der Workflow-Engine.|  
|WinFormsClient|Eine Windows Forms-Clientanwendung, mit der die Benutzer Instanzen des Einkaufsvorgangs erstellen und daran teilnehmen können. Sie verwendet einen benutzerdefinierten Host für die Interaktion mit der Workflow-Engine.|  
  
### <a name="wfdefinition"></a>WfDefinition  
 Die folgende Tabelle enthält eine Beschreibung der wichtigsten Dateien im WfDefinition-Projekt.  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|IPurchaseProcessHost.cs|Schnittstelle für den Host des Workflows|  
|PurchaseProcessHost.cs|Implementierung eines Hosts für den Workflow. Der Host fasst die Details der Workflowlaufzeit zusammen und wird in allen Clientanwendungen verwendet, um die `PurchaseProcess`-Workflowinstanzen zu laden, auszuführen und damit zu interagieren.|  
|PurchaseProcessWorkflow.cs|Eine Aktivität, die die Definition des Einkaufsworkflows (abgeleitet von <xref:System.Activities.Activity>) enthält.<br /><br /> Die Funktionen der Aktivitäten, die sich von <xref:System.Activities.Activity> ableiten, setzten sich aus vorhandenen benutzerdefinierten Aktivitäten und Aktivitäten aus der [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]-Aktivitätenbibliothek zusammen. Das Zusammenfügen dieser Aktivitäten stellt die grundlegendste Möglichkeit für das Erstellen benutzerdefinierter Funktionalität dar.|  
|WaitForVendorProposal.cs|Diese benutzerdefinierte Aktivität leitet sich von <xref:System.Activities.NativeActivity> ab und erstellt ein benanntes Lesezeichen, das später von einem Anbieter beim Abgeben eines Angebots wieder aufgenommen werden muss.<br /><br /> Mit Aktivitäten, die von der <xref:System.Activities.NativeActivity> abgeleitet werden (etwa von der <xref:System.Activities.CodeActivity> abgeleitete Aktivitäten), wird eine imperative Funktionalität erzeugt, indem <xref:System.Activities.NativeActivity.Execute%2A> überschrieben wird. Es besteht jedoch über den <xref:System.Activities.ActivityContext>, der an die `Execute`-Methode weitergegeben wird, Zugriff auf die gesamte Funktionalität der Workflowlaufzeit. Dieser Kontext unterstützt das Planen und Abbrechen untergeordneter Aktivitäten, das Einrichten von Nicht-Persistenzzonen (Ausführungsblöcke, in denen <xref:System.Activities.Bookmark> die Laufzeit die Daten des Workflows nicht persistent hält, z. B. innerhalb atomarer Transaktionen) und Objekte (Handles zum Erneuten Anhalten angehaltener Workflows).|  
|TrackingParticipant.cs|Ein <xref:System.Activities.Tracking.TrackingParticipant>, der alle Nachverfolgungsereignisse empfängt und sie in einer Textdatei speichert.<br /><br /> Nachverfolgungsteilnehmer werden einer Workflowinstanz als Erweiterungen hinzugefügt.|  
|XmlWorkflowInstanceStore.cs|Ein benutzerdefinierter <xref:System.Runtime.DurableInstancing.InstanceStore>, der Workflowanwendungen in XML-Dateien speichert.|  
|XmlPersistenceParticipant.cs|Ein benutzerdefinierter <xref:System.Activities.Persistence.PersistenceParticipant>, der eine Instanz der Ausschreibung in einer XML-Datei speichert.|  
|AsyncResult.cs / CompletedAsyncResult.cs|Hilfsklassen zum Implementieren des asynchronen Musters in den Dauerhaftigkeitskomponenten.|  
  
### <a name="common"></a>Allgemein  
 Die folgende Tabelle enthält eine Beschreibung der wichtigsten Klassen des Common-Projekts.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|Hersteller|Ein Anbieter, der im Rahmen einer Ausschreibung Angebote abgibt.|  
|RequestForProposal|Im Rahmen einer Ausschreibung (Request for Proposal, RFP) werden Anbieter aufgefordert, Angebote für eine bestimmte Ware oder Dienstleistungen abzugeben.|  
|VendorProposal|Ein Angebot, das im Rahmen einer Ausschreibung von einem Anbieter abgegeben wird.|  
|VendorRepository|Das Repository der Anbieter. Diese Implementierung enthält eine im Speicher befindliche Auflistung der Vendor-Instanzen und Methoden zum Bereitstellen dieser Instanzen.|  
|RfpRepository|Das Repository der Ausschreibungen. Diese Implementierung verwendet LINQ to XML für die Abfrage der XML-Datei der Ausschreibung, die von der schematisierten Dauerhaftigkeit erstellt wurde. |  
|IOHelper|Diese Klasse behandelt alle E/A-bezogenen Probleme (Ordner, Pfade usw.)|  
  
### <a name="web-client"></a>Webclient  
 Die folgende Tabelle enthält eine Beschreibung der wichtigsten Webseiten des Webclientprojekts.  
  
|Datei|Beschreibung|  
|-|-|  
|CreateRfp.aspx|Erstellt und sendet eine neue Ausschreibung.|  
|Default.aspx|Zeigt alle aktiven und abgeschlossenen Ausschreibungen an.|  
|GetVendorProposal.aspx|Ruft im Rahmen einer bestimmten Ausschreibung ein Angebot eines Anbieters ab. Diese Seite wird nur von Anbietern verwendet.|  
|ShowRfp.aspx|Zeigt alle Informationen über eine Ausschreibung an (eingegangene Angebote, Daten, Werte usw.). Diese Seite wird nur vom Ersteller der Ausschreibung verwendet.|  
  
### <a name="winforms-client"></a>WinForms-Client  
 Die folgende Tabelle enthält eine Beschreibung der wichtigsten Formulare des Win Forms-Projekts.  
  
|Form|Beschreibung|  
|-|-|  
|NewRfp|Erstellt und sendet eine neue Ausschreibung.|  
|ShowProposals|Zeigt alle aktuellen und abgeschlossenen Ausschreibungen an. **Hinweis:**  Möglicherweise müssen Sie in der Benutzeroberfläche auf die Schaltfläche **Aktualisieren** klicken, um Änderungen in diesem Bildschirm anzuzeigen, nachdem Sie eine Angebotsanforderung erstellt oder geändert haben.|  
|SubmitProposal|Ruft im Rahmen einer bestimmten Ausschreibung ein Angebot eines Anbieters ab. Dieses Fenster wird nur von Anbietern verwendet.|  
|ViewRfp|Zeigt alle Informationen über eine Ausschreibung an (eingegangene Angebote, Daten, Werte usw.). Dieses Fenster wird nur vom Ersteller der Ausschreibung verwendet.|  
  
### <a name="persistence-files"></a>Dauerhaftigkeitsdateien  
 In der folgenden Tabelle sind die Dateien aufgeführt, die vom Dauerhaftigkeitsanbieter (`XmlPersistenceProvider`) erstellt werden. Die Dateien befinden sich im Pfad des TEMP-Ordners des aktuellen Systems (unter Verwendung von <xref:System.IO.Path.GetTempPath%2A>). Die Ablaufverfolgungsdatei wird im aktuellen Ausführungspfad erstellt.  
  
|Dateiname|Beschreibung|`Path`|  
|-|-|-|  
|rfps.xml|Die XML-Datei mit allen aktuellen und abgeschlossenen Ausschreibungen.|<xref:System.IO.Path.GetTempPath%2A>|  
|[Instanz-ID]|Diese Datei enthält alle Informationen zu einer Workflowinstanz.<br /><br /> Diese Datei wird von der schematisierten Dauerhaftigkeitsimplementierung (PersistenceParticipant in XmlPersistenceProvider) generiert.|<xref:System.IO.Path.GetTempPath%2A>|  
|[Instanz-ID].tracking|Eine Textdatei mit allen Ereignissen, die innerhalb einer konkreten Instanz aufgetreten sind.<br /><br /> Diese Datei wird von TrackingParticipant generiert.|<xref:System.IO.Path.GetTempPath%2A>|  
|PurchaseProcess.Tracing.TraceLog.txt|Die Ablaufverfolgungsdatei, die vom Workflow auf Grundlage der Konfigurationsparameter in den Dateien App.config oder Web.config generiert wird.|Aktueller Ausführungspfad|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie mit Visual Studio 2010 die Projektmappendatei PurchaseProcess.sln.  
  
2. Um das Webclientprojekt auszuführen, öffnen Sie **den Projektmappen-Explorer,** und klicken Sie mit der rechten Maustaste auf das **WebClient-Projekt.** Wählen Sie **Als Startprojekt festlegen**aus.  
  
3. Um das WinForms Client-Projekt auszuführen, öffnen Sie den **Projektmappen-Explorer,** und klicken Sie mit der rechten Maustaste auf das **WinForms Client-Projekt.** Wählen Sie **Als Startprojekt festlegen**aus.  
  
4. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
### <a name="web-client-options"></a>Webclientoptionen  
  
- **Erstellen eines neuen RFP**: Erstellt eine neue Vorschlagsanforderung (RFP) und startet einen Einkaufsprozessworkflow.  
  
- **Aktualisieren**: Aktualisiert die Liste der aktiven und beendeten RFPs im Hauptfenster.  
  
- **Ansicht**: Zeigt den Inhalt eines vorhandenen RFP an. Anbieter können ihre Angebote senden (wenn eingeladen oder die Ausschreibung noch nicht beendet ist).  
  
- Ansicht als: Der Benutzer kann mit unterschiedlichen Identitäten auf das RFP zugreifen, indem er den gewünschten Teilnehmer in der **Ansicht als** Kombinationsfeld im aktiven RFPs-Raster auswählt.  
  
### <a name="winforms-client-options"></a>WinForms-Clientoptionen  
  
- **RFP erstellen**: Erstellt eine neue Vorschlagsanforderung (RFP) und startet einen Einkaufsprozessworkflow.  
  
- **Aktualisieren**: Aktualisiert die Liste der aktiven und beendeten RFPs im Hauptfenster.  
  
- **RFP anzeigen**: Zeigt den Inhalt eines vorhandenen RFP an. Anbieter können ihre Angebote senden (wenn eingeladen oder die Ausschreibung noch nicht beendet ist).  
  
- **Connect As**: Der Benutzer kann mit unterschiedlichen Identitäten auf das RFP zugreifen, indem er den gewünschten Teilnehmer in der **Ansicht als** Kombinationsfeld im aktiven RFPs-Raster auswählt.
