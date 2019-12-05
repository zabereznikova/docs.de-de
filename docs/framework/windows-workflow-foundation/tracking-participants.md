---
title: Überwachungsteilnehmer
ms.date: 03/30/2017
ms.assetid: f13e360c-eeb7-4a49-98a0-8f6a52d64f68
ms.openlocfilehash: a033b65125a562307c6247eeda93dcacb31f5382
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837648"
---
# <a name="tracking-participants"></a><span data-ttu-id="c9773-102">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c9773-102">Tracking Participants</span></span>
<span data-ttu-id="c9773-103">Nachverfolgungsteilnehmer sind Erweiterungspunkte, über die ein Workflowentwickler auf <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A>-Objekte zugreifen und sie verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c9773-103">Tracking participants are extensibility points that allow a workflow developer to access <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> objects and process them.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="c9773-104">enthält einen standardmäßigen Überwachungsteilnehmer, der Überwachungsdatensätze als ETW (Ereignisablaufverfolgung für Windows)-Ereignisse schreibt.</span><span class="sxs-lookup"><span data-stu-id="c9773-104">includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="c9773-105">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="c9773-105">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="tracking-participants"></a><span data-ttu-id="c9773-106">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c9773-106">Tracking Participants</span></span>  
 <span data-ttu-id="c9773-107">Die Überwachungsinfrastruktur ermöglicht die Anwendung eines Filters für ausgehende Überwachungsdatensätze, sodass ein Teilnehmer eine Teilmenge der Datensätze abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="c9773-107">The tracking infrastructure allows the application of a filter on the outgoing tracking records such that a participant can subscribe to a subset of the records.</span></span> <span data-ttu-id="c9773-108">Die Anwendung eines Filters erfolgt durch ein Überwachungsprofil.</span><span class="sxs-lookup"><span data-stu-id="c9773-108">The mechanism to apply a filter is through a tracking profile.</span></span>  
  
 <span data-ttu-id="c9773-109">Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] stellt einen nach Verfolgungs Teilnehmer bereit, der die nach Verfolgungs Datensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="c9773-109">Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides a tracking participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="c9773-110">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c9773-110">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="c9773-111">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-111">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="c9773-112">Das SDK-Beispiel für ETW-basierte Überwachung ist eine gute Möglichkeit, über den ETW-basierten Überwachungsteilnehmer mit der WF-Überwachung vertraut zu werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-112">The SDK sample for ETW-based tracking is a good way to get familiar with WF tracking using the ETW-based tracking participant.</span></span>  
  
## <a name="etw-tracking-participant"></a><span data-ttu-id="c9773-113">ETW-Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="c9773-113">ETW Tracking Participant</span></span>  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="c9773-114">enthält einen ETW-Überwachungsteilnehmer, der die Überwachungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="c9773-114">includes an ETW Tracking Participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="c9773-115">Dies geschieht auf sehr effiziente Weise mit minimalen Auswirkungen auf die Leistung der Anwendung oder den Serverdurchsatz.</span><span class="sxs-lookup"><span data-stu-id="c9773-115">This is done in a very efficient manner with minimal impact to the application’s performance or to the server’s throughput.</span></span> <span data-ttu-id="c9773-116">Ein Vorteil der Verwendung des standardmäßigen ETW-Überwachungsteilnehmers besteht darin, dass die empfangenen Überwachungsdatensätze mit den anderen Anwendungs- und Systemprotokollen in der Windows-Ereignisanzeige angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c9773-116">An advantage of using the standard ETW tracking participant is that the tracking records it receives can be viewed with the other application and system logs in the Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="c9773-117">Der standardmäßige ETW-Überwachungsteilnehmer wird, wie im folgenden Beispiel dargestellt, in der Datei "Web.config" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c9773-117">The standard ETW tracking participant is configured in the Web.config file as shown in the following example.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
   <tracking>  
      <profiles>  
        <trackingProfile name="Sample Tracking Profile">  
        ….  
       </trackingProfile>  
      </profiles>  
    </tracking>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="c9773-118">Wenn ein `trackingProfile`-Name nicht angegeben wurde, z. B. nur `<etwTracking/>` oder `<etwTracking profileName=""/>`, wird das mit [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] installierte Standardüberwachungsprofil in der Datei "Machine.config" verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9773-118">If a `trackingProfile` name is not specified, such as just `<etwTracking/>` or `<etwTracking profileName=""/>`, then the default tracking profile installed with the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in the Machine.config file is used.</span></span>  
  
 <span data-ttu-id="c9773-119">In der Datei "Machine.config" abonniert das Standardüberwachungsprofil Workflowinstanz-Datensätze und -fehler.</span><span class="sxs-lookup"><span data-stu-id="c9773-119">In the Machine.config file, the default tracking profile subscribes to workflow instance records and faults.</span></span>  
  
 <span data-ttu-id="c9773-120">In der ETW werden Ereignisse mithilfe einer Anbieter-ID in die ETW-Sitzung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9773-120">In ETW, events are written to the ETW session through a provider ID.</span></span> <span data-ttu-id="c9773-121">Die Anbieter-ID, die der ETW-Überwachungsteilnehmer zum Schreiben der Überwachungsdatensätze in der ETW verwendet, wird im Diagnoseabschnitt der Datei "Web.config" (unter `<system.serviceModel><diagnostics>`) definiert.</span><span class="sxs-lookup"><span data-stu-id="c9773-121">The provider ID that the ETW tracking participant uses for writing the tracking records to ETW is defined in the diagnostics section of the Web.config file (under `<system.serviceModel><diagnostics>`).</span></span> <span data-ttu-id="c9773-122">In der Regel verwendet der ETW-Überwachungsteilnehmer, wie im folgenden Beispiel dargestellt, eine standardmäßige Anbieter-ID, wenn keine angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c9773-122">By default, the ETW tracking participant uses a default provider ID when one has not been specified, as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
        <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />  
```  
  
 <span data-ttu-id="c9773-123">Die folgende Abbildung zeigt den Überwachungsdatenstrom über den ETW-Überwachungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="c9773-123">The following illustration shows the flow of tracking data through the ETW tracking participant.</span></span> <span data-ttu-id="c9773-124">Sobald die Überwachungsdaten die ETW-Sitzung erreichen, kann auf unterschiedliche Weise darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-124">Once the tracking data reaches the ETW session, it can be accessed in a number of ways.</span></span> <span data-ttu-id="c9773-125">Eine der besten Möglichkeiten für den Zugriff auf diese Ereignisse ist die Ereignisanzeige, ein häufig verwendetes Windows-Tool für die Anzeige von Protokollen und Ablaufverfolgungen von Anwendungen und Diensten.</span><span class="sxs-lookup"><span data-stu-id="c9773-125">One of the most useful ways to access these events is through Event Viewer, a common Windows tool used for viewing logs and traces from applications and services.</span></span>  
  
 ![Fluss der Überwachungsdaten über den etw-Überwachungs Anbieter.](./media/tracking-participants/tracking-data-event-tracing-windows-provider.gif)  
  
## <a name="tracking-participant-event-data"></a><span data-ttu-id="c9773-127">Ereignisdaten von Überwachungsteilnehmern</span><span class="sxs-lookup"><span data-stu-id="c9773-127">Tracking Participant Event Data</span></span>  
 <span data-ttu-id="c9773-128">Ein Überwachungsteilnehmer serialisiert verfolgte Ereignisdaten in einer ETW-Sitzung jeweils im Format von einem Ereignis pro Überwachungsdatensatz.</span><span class="sxs-lookup"><span data-stu-id="c9773-128">A tracking participant serializes tracked event data to an ETW session in the format of one event per tracking record.</span></span>  <span data-ttu-id="c9773-129">Ein Ereignis wird innerhalb des Bereichs von 100 bis 199 durch eine ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c9773-129">An event is identified using an ID within the range of 100 through 199.</span></span> <span data-ttu-id="c9773-130">Informationen zu Definitionen der von einem nach Verfolgungs Teilnehmer ausgegebenen Überwachungs Ereignisdaten Sätze finden Sie im Referenz Thema zu [Überwachungs Ereignissen](tracking-events-reference.md) .</span><span class="sxs-lookup"><span data-stu-id="c9773-130">For definitions of the tracking event records emitted by a tracking participant, see the [Tracking Events Reference](tracking-events-reference.md) topic.</span></span>  
  
 <span data-ttu-id="c9773-131">Die Größe eines ETW-Ereignisses wird durch die Größe des ETW-Puffers oder durch die maximale Nutzlast für ein ETW-Ereignis beschränkt, wobei jeweils der niedrigere Wert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9773-131">The size of an ETW event is limited by the ETW buffer size, or the by the maximum payload for an ETW event, whichever value is smaller.</span></span> <span data-ttu-id="c9773-132">Wenn die Größe des Ereignisses beide ETW-Grenzen überschreitet, wird das Ereignis abgeschnitten und sein Inhalt willkürlich entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9773-132">If the size of the event exceeds either of these ETW limits, the event is truncated and its content removed in an arbitrary manner.</span></span> <span data-ttu-id="c9773-133">Variablen, Argumente, Anmerkungen und benutzerdefinierte Daten werden nicht selektiv entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9773-133">Variables, arguments, annotations and custom data are not selectively removed.</span></span> <span data-ttu-id="c9773-134">Bei abgeschnittenen Daten werden alle Daten abgeschnitten, unabhängig davon, welcher Wert zur Überschreitung der ETW-Grenze für die Ereignisgröße geführt hat.</span><span class="sxs-lookup"><span data-stu-id="c9773-134">In the case of truncation, all of these are truncated regardless of the value that caused the event size to exceed the ETW limit.</span></span>  <span data-ttu-id="c9773-135">Die entfernten Daten werden durch `<item>..<item>` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c9773-135">The removed data is replaced with `<item>..<item>`.</span></span>  
  
 <span data-ttu-id="c9773-136">Komplexe Typen in Variablen, Argumenten und benutzerdefinierten Datenelementen werden mit der <xref:System.Runtime.Serialization.NetDataContractSerializer>-Klasse in den etw-Ereignisdaten Satz serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c9773-136">Complex types in variables, arguments, and custom data items are serialized to the ETW event record using the <xref:System.Runtime.Serialization.NetDataContractSerializer> class.</span></span> <span data-ttu-id="c9773-137">Diese Klasse enthält Informationen zum CLR-Typ im serialisierten XML-Stream.</span><span class="sxs-lookup"><span data-stu-id="c9773-137">This class includes CLR-type information in the serialized XML steam.</span></span>  
  
 <span data-ttu-id="c9773-138">Aufgrund der ETW-Beschränkung abgeschnittene Nutzlastdaten können dazu führen, dass Überwachungsdatensätze mehrfach an eine ETW-Sitzung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-138">Truncation of payload data due to ETW limits can result in duplicate tracking records being sent to an ETW session.</span></span> <span data-ttu-id="c9773-139">Dies kann geschehen, wenn mehr als eine Sitzung die Ereignisse überwacht und die Sitzungen unterschiedliche Nutzlastgrenzen für die Ereignisse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c9773-139">This can occur if more than one session is listening for the events and the sessions have different payload limits for the events.</span></span>  
  
 <span data-ttu-id="c9773-140">Bei der Sitzung mit der niedrigeren Begrenzung wird das Ereignis möglicherweise abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="c9773-140">For  the session with the lower limit the event may be truncated.</span></span> <span data-ttu-id="c9773-141">Der ETW-Überwachungsteilnehmer hat keine Informationen zur Anzahl von Sitzungen, die die Ereignisse überwachen. Wenn ein Ereignis für eine Sitzung abgeschnitten wird, versucht der ETW-Teilnehmer noch ein Mal, das Ereignis zu senden.</span><span class="sxs-lookup"><span data-stu-id="c9773-141">The ETW tracking participant does not have any knowledge of the number of sessions listening for the events; if an event is truncated for a session then the ETW participant retries sending the event once.</span></span> <span data-ttu-id="c9773-142">In diesem Fall empfängt die Sitzung, für die eine höhere Nutzlastgröße konfiguriert ist, das Ereignis zweimal (das nicht abgeschnittene und das abgeschnittene Ereignis).</span><span class="sxs-lookup"><span data-stu-id="c9773-142">In this case the session that is configured to accept a larger payload size will get the event twice (the non-truncated and truncated event).</span></span> <span data-ttu-id="c9773-143">Diese Duplizierung kann verhindert werden, indem für alle ETW-Sitzungen die gleichen Begrenzungen der Puffergröße konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-143">Duplication can be prevented by configuring all the ETW sessions with same buffer size limits.</span></span>  
  
## <a name="accessing-tracking-data-from-an-etw-participant-in-the-event-viewer"></a><span data-ttu-id="c9773-144">Zugreifen auf Überwachungsdaten über einen ETW-Teilnehmer in der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="c9773-144">Accessing Tracking Data from an ETW Participant in the Event Viewer</span></span>  
 <span data-ttu-id="c9773-145">Sie können über die Ereignisanzeige auf Ereignisse zugreifen, die vom ETW-Überwachungsteilnehmer in eine ETW-Sitzung geschrieben werden, falls die standardmäßige Anbieter-ID verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9773-145">Events that are written to an ETW session by the ETW tracking participant can be accessed through the Event Viewer (when using the default provider ID).</span></span> <span data-ttu-id="c9773-146">Auf diese Weise können Überwachungsdatensätze, die vom Workflow ausgegeben wurden, schnell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-146">This allows for rapidly viewing of tracking records that have been emitted by the workflow.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9773-147">Überwachungsdatensatz-Ereignisse, die an eine ETW-Sitzung ausgegeben werden, verwenden Ereignis-IDs im Bereich von 100 bis 199.</span><span class="sxs-lookup"><span data-stu-id="c9773-147">Tracking record events emitted to an ETW session use event IDs in the range of 100 through 199.</span></span>  
  
#### <a name="to-enable-viewing-the-tracking-records-in-event-viewer"></a><span data-ttu-id="c9773-148">So aktivieren Sie das Anzeigen der Überwachungsdatensätze in der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="c9773-148">To enable viewing the Tracking Records in Event Viewer</span></span>  
  
1. <span data-ttu-id="c9773-149">Starten der Ereignisanzeige (EVENTVWR.EXE)</span><span class="sxs-lookup"><span data-stu-id="c9773-149">Start the Event Viewer (EVENTVWR.EXE)</span></span>  
  
2. <span data-ttu-id="c9773-150">Wählen Sie **Ereignisanzeige, Anwendungs-und Dienst Protokolle, Microsoft, Windows, Anwendungs Server-Anwendungen**aus.</span><span class="sxs-lookup"><span data-stu-id="c9773-150">Select **Event Viewer, Applications and Services Logs, Microsoft, Windows, Application Server-Applications**.</span></span>  
  
3. <span data-ttu-id="c9773-151">Klicken Sie mit der rechten Maustaste, und stellen Sie sicher, dass **Ansicht, analytische und Debugprotokolle anzeigen** ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="c9773-151">Right-click and ensure that **View, Show Analytic and Debug logs** is selected.</span></span> <span data-ttu-id="c9773-152">Wenn dies nicht der Fall ist, aktivieren Sie die Option, sodass das Häkchen daneben angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c9773-152">If not, select it so the check mark appears next to it.</span></span> <span data-ttu-id="c9773-153">Dadurch werden die Protokolle " **analytische**", " **perf**" und " **Debug** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9773-153">This displays the **Analytic**, **Perf**, and **Debug** logs.</span></span>  
  
4. <span data-ttu-id="c9773-154">Klicken Sie mit der rechten Maustaste auf das **analytische** Protokoll, und wählen Sie **Protokoll aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="c9773-154">Right-click the **Analytic** log and then select **Enable Log**.</span></span> <span data-ttu-id="c9773-155">Das Protokoll befindet sich in der Datei unter "%SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl".</span><span class="sxs-lookup"><span data-stu-id="c9773-155">The log will exist in the %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl file.</span></span>  
  
## <a name="custom-tracking-participant"></a><span data-ttu-id="c9773-156">Benutzerdefinierte Nachverfolgungskomponente</span><span class="sxs-lookup"><span data-stu-id="c9773-156">Custom Tracking Participant</span></span>  
 <span data-ttu-id="c9773-157">Die Überwachungsteilnehmer-API ermöglicht eine Erweiterung der Überwachungslaufzeit mit einem vom Benutzer bereitgestellten Überwachungsteilnehmer. Dieser kann benutzerdefinierte Logik enthalten, mit der von der Workflowlaufzeit ausgegebene Überwachungsdatensätze behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c9773-157">The tracking participant API allows extension of the tracking runtime with a user-provided tracking participant that can include custom logic to handle tracking records emitted by the workflow runtime.</span></span> <span data-ttu-id="c9773-158">Zum Schreiben eines benutzerdefinierten Überwachungsteilnehmers muss der Entwickler die `Track`-Methode für die <xref:System.Activities.Tracking.TrackingParticipant>-Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="c9773-158">To write a custom tracking participant, the developer must implement the `Track` method on the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="c9773-159">Diese Methode wird aufgerufen, wenn ein Überwachungsdatensatz von der Workflowlaufzeit ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c9773-159">This method is called when a tracking record is emitted by the workflow runtime.</span></span>  
  
 <span data-ttu-id="c9773-160">Überwachungsteilnehmer sind von der <xref:System.Activities.Tracking.TrackingParticipant>-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c9773-160">Tracking participants derive from the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="c9773-161">Das vom System bereitgestellte <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt gibt ein ETW (Ereignisablaufverfolgung für Windows)-Ereignis für jeden empfangenen Überwachungsdatensatz aus.</span><span class="sxs-lookup"><span data-stu-id="c9773-161">The system-provided <xref:System.Activities.Tracking.EtwTrackingParticipant> emits an Event Tracking for Windows (ETW) event for each tracking record that is received.</span></span> <span data-ttu-id="c9773-162">Zum Erstellen eines benutzerdefinierten Überwachungsteilnehmers wird eine Klasse erstellt, die von <xref:System.Activities.Tracking.TrackingParticipant> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="c9773-162">To create a custom tracking participant, a class is created that derives from <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="c9773-163">Um grundlegende Funktionen für Nachverfolgung bereitzustellen, überschreiben Sie <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9773-163">To provide basic tracking functionality, override <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span></span> <span data-ttu-id="c9773-164"><xref:System.Activities.Tracking.TrackingParticipant.Track%2A> wird aufgerufen, wenn ein Nachverfolgungsdatensatz von der Laufzeit gesendet wird und wie gewünscht verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9773-164"><xref:System.Activities.Tracking.TrackingParticipant.Track%2A> is called when a tracking record is sent by the runtime and can be processed in the desired manner.</span></span> <span data-ttu-id="c9773-165">Im folgenden Beispiel wird eine benutzerdefinierte Überwachungsteilnehmer-Klasse definiert, die alle Überwachungsdatensätze an das Konsolenfenster ausgibt.</span><span class="sxs-lookup"><span data-stu-id="c9773-165">In the following example, a custom tracking participant class is defined that emits all tracking records to the console window.</span></span> <span data-ttu-id="c9773-166">Sie können auch ein <xref:System.Activities.Tracking.TrackingParticipant>-Objekt implementieren, das die Überwachungsdatensätze mit der `BeginTrack`-Methode und der `EndTrack`-Methode asynchron verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c9773-166">You can also implement a <xref:System.Activities.Tracking.TrackingParticipant> object that processes the tracking records asynchronously using its `BeginTrack` and `EndTrack` methods</span></span>  
  
```csharp  
class ConsoleTrackingParticipant : TrackingParticipant  
{  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        if (record != null)  
        {  
            Console.WriteLine("=================================");  
            Console.WriteLine(record);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c9773-167">Wenn Sie einen bestimmten Überwachungsteilnehmer verwenden möchten, registrieren Sie diesen, wie im folgenden Beispiel gezeigt, für die Workflowinstanz, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9773-167">To use a particular tracking participant, register it with the workflow instance that you want to track, as shown in the following example.</span></span>  
  
```csharp  
myInstance.Extensions.Add(new ConsoleTrackingParticipant());  
```  
  
 <span data-ttu-id="c9773-168">Im folgenden Beispiel wird ein Workflow erstellt, der aus einer <xref:System.Activities.Statements.Sequence>-Aktivität mit einer <xref:System.Activities.Statements.WriteLine>-Aktivität besteht.</span><span class="sxs-lookup"><span data-stu-id="c9773-168">In the following example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> activity that contains a <xref:System.Activities.Statements.WriteLine> activity is created.</span></span> <span data-ttu-id="c9773-169">Der `ConsoleTrackingParticipant` wird den Erweiterungen hinzugefügt, und der Workflow wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c9773-169">The `ConsoleTrackingParticipant` is added to the extensions and the workflow is invoked.</span></span>  
  
```csharp  
Activity activity= new Sequence()  
{  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "Hello World."  
        }  
    }  
};  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
  
instance.Extensions.Add(new ConsoleTrackingParticipant());  
  instance.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
            {  
                Console.WriteLine("workflow instance completed, Id = " + instance.Id);  
                resetEvent.Set();  
            };  
            instance.Run();  
            Console.ReadLine();  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9773-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9773-170">See also</span></span>

- <span data-ttu-id="c9773-171">[Windows Server-App-Fabric-Überwachung](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c9773-171">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="c9773-172">[Überwachen von Anwendungen mit App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c9773-172">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
