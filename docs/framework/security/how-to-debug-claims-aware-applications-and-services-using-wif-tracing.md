---
title: "Vorgehensweise: Debuggen von Ansprüche-unterstützenden Anwendungen und Diensten mittels WIF-Ablaufverfolgung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4243313d88b22aa9f755a3586ea0c5fbe08cd891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="d943d-102">Vorgehensweise: Debuggen von Ansprüche-unterstützenden Anwendungen und Diensten mittels WIF-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d943d-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="d943d-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="d943d-103">Applies To</span></span>  
  
-   <span data-ttu-id="d943d-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="d943d-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="d943d-105">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="d943d-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
-   <span data-ttu-id="d943d-106">Problembehandlung und Debuggen von WIF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d943d-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d943d-107">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d943d-107">Summary</span></span>  
 <span data-ttu-id="d943d-108">Diese Anleitungen beschreiben die erforderlichen Schritte zum Konfigurieren der WIF-Ablaufverfolgung, zum Sammeln von Protokollen und zum Analysieren der Ablaufverfolgungsprotokolle mit dem Trace Viewer-Tool.</span><span class="sxs-lookup"><span data-stu-id="d943d-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="d943d-109">Dieses Tool stellt eine allgemeine Zuordnung zwischen Protokolleinträgen und Aktionen bereit, die für die Behebung von WIF-bezogenen Problemen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d943d-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="d943d-110">Inhalt</span><span class="sxs-lookup"><span data-stu-id="d943d-110">Contents</span></span>  
  
-   <span data-ttu-id="d943d-111">Ziele</span><span class="sxs-lookup"><span data-stu-id="d943d-111">Objectives</span></span>  
  
-   <span data-ttu-id="d943d-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="d943d-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d943d-113">Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"</span><span class="sxs-lookup"><span data-stu-id="d943d-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="d943d-114">Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools</span><span class="sxs-lookup"><span data-stu-id="d943d-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="d943d-115">Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen</span><span class="sxs-lookup"><span data-stu-id="d943d-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
-   <span data-ttu-id="d943d-116">Verwandte Elemente</span><span class="sxs-lookup"><span data-stu-id="d943d-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="d943d-117">Ziele</span><span class="sxs-lookup"><span data-stu-id="d943d-117">Objectives</span></span>  
  
-   <span data-ttu-id="d943d-118">Konfigurieren der WIF-Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="d943d-118">Configure WIF tracing.</span></span>  
  
-   <span data-ttu-id="d943d-119">Anzeigen von Ablaufverfolgungsprotokollen im Trace Viewer-Tool.</span><span class="sxs-lookup"><span data-stu-id="d943d-119">View trace logs in the Trace Viewer tool.</span></span>  
  
-   <span data-ttu-id="d943d-120">Identifizieren von WIF-bezogenen Problemen in den Ablaufverfolgungsprotokollen.</span><span class="sxs-lookup"><span data-stu-id="d943d-120">Identify WIF related issues in the trace logs.</span></span>  
  
-   <span data-ttu-id="d943d-121">Anwenden von Korrekturmaßnahmen auf WIF-bezogene Probleme, die in den Ablaufverfolgungsprotokollen gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="d943d-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="d943d-122">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="d943d-122">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d943d-123">Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"</span><span class="sxs-lookup"><span data-stu-id="d943d-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="d943d-124">Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools</span><span class="sxs-lookup"><span data-stu-id="d943d-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="d943d-125">Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen</span><span class="sxs-lookup"><span data-stu-id="d943d-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="d943d-126">Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"</span><span class="sxs-lookup"><span data-stu-id="d943d-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="d943d-127">In diesem Schritt fügen Sie Konfigurationsabschnitten in der Datei *Web.config* Änderungen hinzu, damit WIF die zugehörigen Ereignisse verfolgen und in einem Ablaufverfolgungsprotokoll speichern kann.</span><span class="sxs-lookup"><span data-stu-id="d943d-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="d943d-128">So konfigurieren Sie die WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"</span><span class="sxs-lookup"><span data-stu-id="d943d-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1.  <span data-ttu-id="d943d-129">Öffnen Sie die Stammkonfigurationsdatei **Web.config** oder **App.config** im Visual Studio-Editor, indem Sie im **Projektmappen-Explorer** darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="d943d-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="d943d-130">Wenn Ihre Projektmappe die Konfigurationsdatei **Web.config** bzw. **App.config** nicht enthält, müssen Sie diese hinzufügen. Klicken Sie dazu mit der rechten Maustaste im **Projektmappen-Explorer** auf die Projektmappe, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element…**.</span><span class="sxs-lookup"><span data-stu-id="d943d-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="d943d-131">Wählen Sie im Dialogfeld **Neues Element** die **Anwendungskonfigurationsdatei** (für **App.config**) oder die **Webkonfigurationsdatei** (für **Web.config**) aus der Liste aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d943d-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2.  <span data-ttu-id="d943d-132">Fügen Sie in der Konfigurationsdatei dem **\<configuration>**-Knoten am Ende der Datei Konfigurationseinträge hinzu, die in etwa wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="d943d-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3.  <span data-ttu-id="d943d-133">Die obige Konfiguration weist WIF an, ausführliche Ablaufverfolgungsereignisse zu erstellen und in der Datei *WIFTrace.e2e* zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="d943d-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="d943d-134">Eine vollständige Liste der Werte für das **switchValue**-Attribut finden Sie in der Tabelle mit den Ablaufverfolgungsebenen im folgenden Thema: [Configuring Tracing (Konfigurieren der Ablaufverfolgung)](http://msdn.microsoft.com/library/ms733025.aspx).</span><span class="sxs-lookup"><span data-stu-id="d943d-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](http://msdn.microsoft.com/library/ms733025.aspx).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="d943d-135">Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools</span><span class="sxs-lookup"><span data-stu-id="d943d-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="d943d-136">In diesem Schritt verwenden Sie das Trace Viewer-Tool (SvcTraceViewer.exe), um WIF-Ablaufverfolgungsprotokolle zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="d943d-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="d943d-137">So analysieren Sie WIF-Ablaufverfolgungsprotokolle mit dem Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="d943d-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1.  <span data-ttu-id="d943d-138">Das Trace Viewer-Tool (SvcTraceViewer.exe) ist im Windows SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="d943d-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="d943d-139">Wenn Sie das Windows SDK noch nicht installiert haben, können Sie es hier herunterladen: [Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="d943d-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2.  <span data-ttu-id="d943d-140">Führen Sie das Trace Viewer-Tool (SvcTraceViewer.exe) aus.</span><span class="sxs-lookup"><span data-stu-id="d943d-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="d943d-141">Es befindet sich in der Regel im Installationspfad im Ordner **Bin**.</span><span class="sxs-lookup"><span data-stu-id="d943d-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3.  <span data-ttu-id="d943d-142">Öffnen Sie die WIF-Ablaufverfolgungsprotokolldatei, zum Beispiel „WIFTrace.e2e“, indem Sie im Menü auf **Datei**, **Öffnen...** klicken.</span><span class="sxs-lookup"><span data-stu-id="d943d-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="d943d-143">oder die Tastenkombination **Strg+O** verwenden.</span><span class="sxs-lookup"><span data-stu-id="d943d-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="d943d-144">Die Ablaufverfolgungsprotokolldatei wird im Trace Viewer-Tool geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d943d-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4.  <span data-ttu-id="d943d-145">Überprüfen Sie die Einträge auf der Registerkarte **Aktivität**. Jeder Eintrag muss eine Aktivitätsnummer, die Anzahl der protokollierten Ablaufverfolgungen, die Dauer der Aktivität sowie Zeitstempel für Anfang und Ende der Aktivität enthalten.</span><span class="sxs-lookup"><span data-stu-id="d943d-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5.  <span data-ttu-id="d943d-146">Klicken Sie auf die Registerkarte **Aktivität**. Im Hauptbereich des Tools sollten ausführliche Ablaufverfolgungseinträge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d943d-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="d943d-147">Filtern Sie die Einträge mithilfe der Dropdownliste **Ebene**, die im Menü zur Verfügung steht, nach den einzelnen Ablaufverfolgungsebenen, z.B. **Alle**, **Warnung**, **Fehler**, **Informationen** usw.</span><span class="sxs-lookup"><span data-stu-id="d943d-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6.  <span data-ttu-id="d943d-148">Klicken Sie auf bestimmte Ablaufverfolgungseinträge, um die Einzelheiten im unteren Bereich des Tools zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d943d-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="d943d-149">Die Einzelheiten können in den Ansichten **Formatiert** und **XML** angezeigt werden. Wählen Sie die jeweils entsprechende Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="d943d-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="d943d-150">Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen</span><span class="sxs-lookup"><span data-stu-id="d943d-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="d943d-151">In diesem Schritt ermitteln Sie mithilfe des WIF-Ablaufverfolgungsprotokolls und des Trace Viewer-Tools Lösungen für identifizierte WIF-bezogene Probleme.</span><span class="sxs-lookup"><span data-stu-id="d943d-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="d943d-152">Dieses Tool zeigt allgemeine Zuordnungen zwischen WIF-bezogenen Ausnahmen und möglichen Lösungen oder Aktionen auf, die zum Beheben des Problems erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d943d-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="d943d-153">So identifizieren Sie Lösungen zum Beheben WIF-bezogener Probleme</span><span class="sxs-lookup"><span data-stu-id="d943d-153">To identify solutions to fix WIF related issues</span></span>  
  
1.  <span data-ttu-id="d943d-154">Überprüfen Sie in der folgenden Tabelle die WIF-Ausnahmen und die Aktionen, die zum Beheben der Probleme erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d943d-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="d943d-155">**Fehler-ID**</span><span class="sxs-lookup"><span data-stu-id="d943d-155">**Error ID**</span></span>|<span data-ttu-id="d943d-156">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="d943d-156">**Error Message**</span></span>|<span data-ttu-id="d943d-157">**Aktion zum Beheben des Fehlers**</span><span class="sxs-lookup"><span data-stu-id="d943d-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="d943d-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="d943d-158">ID4175</span></span>|<span data-ttu-id="d943d-159">Der Aussteller des Sicherheitstokens wurde von der IssuerNameRegistry nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="d943d-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="d943d-160">Konfigurieren Sie die IssuerNameRegistry, um einen gültigen Name für diesen Aussteller zurückzugeben und die Sicherheitstoken dieses Ausstellers zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d943d-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="d943d-161">Dieser Fehler kann entstehen, wenn Sie einen Fingerabdruck aus dem MMC-Snap-In kopieren und in die Datei *Web.config* einfügen.</span><span class="sxs-lookup"><span data-stu-id="d943d-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="d943d-162">Insbesondere beim Kopieren des Fingerabdrucks aus dem Fenster mit den Zertifikateigenschaften kann es passieren, dass ein zusätzliches, nicht druckbares Zeichen in die Zeichenfolge eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d943d-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="d943d-163">Durch dieses zusätzliche Zeichen stimmt der Fingerabdruck nicht mehr überein. Wie Sie den Fingerabdruck richtig kopieren, ist hier beschrieben: [http://msdn.microsoft.com/library/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)</span><span class="sxs-lookup"><span data-stu-id="d943d-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found here: [http://msdn.microsoft.com/library/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="d943d-164">Verwandte Elemente</span><span class="sxs-lookup"><span data-stu-id="d943d-164">Related Items</span></span>  
  
-   [<span data-ttu-id="d943d-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="d943d-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](http://msdn.microsoft.com/library/aa751795.aspx)
