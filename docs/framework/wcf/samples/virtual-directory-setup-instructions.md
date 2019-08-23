---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: f755fadf6bef2bdd58fd31f3460a143b8f52eddf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966738"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="172b7-102">Anleitung zum Einrichten eines virtuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="172b7-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="172b7-103">Die Windows Communication Foundation (WCF)-Beispiele sind dafür vorgesehen, ein gemeinsames virtuelles Verzeichnis namens "Service Model Samples" freizugeben, das dem Ordner "%SystemDrive%\inetpub\wwwroot\servicemodelsamples" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="172b7-104">% SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="172b7-105">Sie können die Dateien Setupvroot. bat und Cleanupvroot. bat aus dem [einmaligen Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausführen, um das virtuelle Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="172b7-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="172b7-106">Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="172b7-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="172b7-107">Verfahren</span><span class="sxs-lookup"><span data-stu-id="172b7-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="172b7-108">So erstellen Sie ein virtuelles Verzeichnis in IIS 7,0 oder 7,5</span><span class="sxs-lookup"><span data-stu-id="172b7-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="172b7-109">Klicken Sie im Startmenü auf **Ausführen**, und geben Sie **inetmgr** ein, um das MMC-Snap-in Internetinformationsdienste (IIS) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="172b7-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="172b7-110">Erweitern Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann den Knoten **Standorte** .</span><span class="sxs-lookup"><span data-stu-id="172b7-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="172b7-111">Klicken Sie mit der rechten Maustaste auf **Standard Website**, und wählen Sie **Anwendung hinzufügen** aus, um das **Fenster Anwendung hinzufügen**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="172b7-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="172b7-112">Geben `servicemodelsamples` Sie im Fenster als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="172b7-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="172b7-113">Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="172b7-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="172b7-114">Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="172b7-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="172b7-115">Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="172b7-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="172b7-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="172b7-116">Click **OK**.</span></span> <span data-ttu-id="172b7-117">Die Webanwendung wird für die WCF-Beispiele erstellt.</span><span class="sxs-lookup"><span data-stu-id="172b7-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="172b7-118">Diese Aufgabe muss nur einmal ausgeführt werden, da für alle WCF-Beispiele dieselbe Webanwendung Service Model Samples verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="172b7-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="172b7-119">In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.</span><span class="sxs-lookup"><span data-stu-id="172b7-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="172b7-120">Zusätzlich zum Erstellen des virtuellen Verzeichnisses müssen Sie auch seine Eigenschaften festlegen, um das Ausführen von WCF-Diensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="172b7-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="172b7-121">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="172b7-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="172b7-122">So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0</span><span class="sxs-lookup"><span data-stu-id="172b7-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="172b7-123">Öffnen Sie ein Eingabe Aufforderungs Fenster `start inetmgr` , und geben Sie ein, um das MMC-Snap-in Internetinformationsdienste (IIS) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="172b7-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="172b7-124">Erweitern Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann den Knoten **Websites** .</span><span class="sxs-lookup"><span data-stu-id="172b7-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="172b7-125">Klicken Sie mit der rechten Maustaste auf **Standard Website** , und wählen Sie **neu, virtuelles Verzeichnis** , um den Assistenten zum Erstellen virtueller Verzeichnisse zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="172b7-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="172b7-126">Geben `servicemodelsamples` Sie im Assistenten als Alias für das virtuelle Verzeichnis ein, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="172b7-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="172b7-127">Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="172b7-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="172b7-128">Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="172b7-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="172b7-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="172b7-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="172b7-130">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="172b7-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="172b7-131">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="172b7-131">**Read**</span></span>  
  
    - <span data-ttu-id="172b7-132">**Skripts ausführen (z. b. ASP)**</span><span class="sxs-lookup"><span data-stu-id="172b7-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="172b7-133">Klicken Sie auf **weiter**, und klicken Sie dann auf **Fertig** stellen, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="172b7-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="172b7-134">Diese Aufgabe muss nur einmal ausgeführt werden, da für alle WCF-Beispiele dasselbe virtuelle Verzeichnis Service Model Samples verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="172b7-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="172b7-135">So legen Sie zusätzliche Eigenschaften für virtuelle Verzeichnisse in IIS 7,0 oder 7,5 fest</span><span class="sxs-lookup"><span data-stu-id="172b7-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="172b7-136">Klicken Sie auf den Knoten servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="172b7-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="172b7-137">Unten im Fenster sind zwei Ansichten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="172b7-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="172b7-138">Wählen Sie Featureansicht aus, wenn Sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="172b7-139">Doppelklicken Sie auf den Eintrag für **Verzeichnis durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="172b7-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="172b7-140">Wählen Sie im Bereich Aktionen die Option **aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="172b7-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="172b7-141">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="172b7-142">Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="172b7-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="172b7-143">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="172b7-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="172b7-144">So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest</span><span class="sxs-lookup"><span data-stu-id="172b7-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="172b7-145">Klicken Sie mit der rechten Maustaste auf den Knoten Service Model Samples, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="172b7-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="172b7-146">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="172b7-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="172b7-147">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="172b7-147">**Read**</span></span>  
  
    - <span data-ttu-id="172b7-148">**Protokoll Besuche**</span><span class="sxs-lookup"><span data-stu-id="172b7-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="172b7-149">**Diese Ressource indizieren**</span><span class="sxs-lookup"><span data-stu-id="172b7-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="172b7-150">Aktivieren Sie das Kontrollkästchen **Verzeichnis durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="172b7-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="172b7-151">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="172b7-152">So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7,0 oder 7,5 fest</span><span class="sxs-lookup"><span data-stu-id="172b7-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="172b7-153">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="172b7-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="172b7-154">Klicken Sie mit der rechten Maustaste auf den Ordner Service Model Samples, und klicken Sie auf **Freigeben** oder **Freigeben mit**.</span><span class="sxs-lookup"><span data-stu-id="172b7-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="172b7-155">Klicken Sie auf den Pfeil nach unten auf der linken Seite der Schaltfläche **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="172b7-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="172b7-156">Wählen Sie den Eintrag **Suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="172b7-156">Select the **Find** entry.</span></span> <span data-ttu-id="172b7-157">Das Fenster **Benutzer oder Gruppen auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="172b7-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="172b7-158">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="172b7-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="172b7-159">Klicken Sie auf **Standorte**.</span><span class="sxs-lookup"><span data-stu-id="172b7-159">Click **Locations**.</span></span> <span data-ttu-id="172b7-160">Das Fenster Speicher **Orte** ist nun geöffnet.</span><span class="sxs-lookup"><span data-stu-id="172b7-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="172b7-161">Wählen Sie den Eintrag für den verwendeten Computer aus.</span><span class="sxs-lookup"><span data-stu-id="172b7-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="172b7-162">Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="172b7-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="172b7-163">Nachdem Sie den Computer ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="172b7-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="172b7-164">Klicken Sie auf **Jetzt suchen**.</span><span class="sxs-lookup"><span data-stu-id="172b7-164">Click **Find Now**.</span></span> <span data-ttu-id="172b7-165">Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="172b7-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="172b7-166">Suchen Sie den Eintrag **IIS_IUSRS** in der Spalte **Name (Relative Distinguished Name)** .</span><span class="sxs-lookup"><span data-stu-id="172b7-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="172b7-167">Wählen Sie diesen Eintrag aus, und klicken Sie auf **OK** , um das Fenster Suchergebnisse zu schließen</span><span class="sxs-lookup"><span data-stu-id="172b7-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="172b7-168">Klicken Sie auf **OK** , um das Fenster **Benutzer oder Gruppen auswählen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="172b7-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="172b7-169">Klicken Sie auf **Freigeben** , um die Änderungen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="172b7-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="172b7-170">Nachdem die Änderungen zum Aktivieren der Freigabe abgeschlossen sind, klicken Sie auf **Fertig** , um das Fenster **Dateifreigabe** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="172b7-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="172b7-171">So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein</span><span class="sxs-lookup"><span data-stu-id="172b7-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="172b7-172">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="172b7-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="172b7-173">Klicken Sie mit der rechten Maustaste auf den Ordner **Service Model Samples** , und klicken Sie dann auf **Freigabe und Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="172b7-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="172b7-174">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="172b7-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="172b7-175">Wenn Sie IIS 6,0 verwenden, überprüfen Sie im Feld **Gruppen-oder Benutzernamen** , ob das **Internet Gastkonto** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="172b7-176">Falls der Eintrag nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="172b7-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="172b7-177">Klicken Sie auf **Start** und anschließend auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="172b7-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="172b7-178">Wenn das Symbol " **Benutzerkonten** " nicht angezeigt wird, klicken Sie auf **zur Kategorieansicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="172b7-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="172b7-179">Klicken Sie auf das Symbol **Benutzerkonten** .</span><span class="sxs-lookup"><span data-stu-id="172b7-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="172b7-180">Klicken Sie unter "oder wählen Sie ein System Steuerungs Symbol" auf **Benutzerkonten**.</span><span class="sxs-lookup"><span data-stu-id="172b7-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="172b7-181">Klicken Sie im Dialogfeld **Benutzerkonten** auf die Registerkarte **erweitert** .</span><span class="sxs-lookup"><span data-stu-id="172b7-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="172b7-182">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="172b7-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="172b7-183">Klicken Sie im Dialogfeld **lokale Benutzer und Gruppen** auf den Ordner **Benutzer** , um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="172b7-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="172b7-184">Doppelklicken Sie im rechten Bereich auf **Internet Gastkonto**.</span><span class="sxs-lookup"><span data-stu-id="172b7-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="172b7-185">Kopieren Sie im Dialogfeld **Eigenschaften** den Namen, der als Internet Gastkonto verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="172b7-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="172b7-186">Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="172b7-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="172b7-187">Schließen Sie das Dialogfeld **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="172b7-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="172b7-188">Schließen Sie das Dialogfeld **lokale Benutzer und Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="172b7-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="172b7-189">Schließen Sie das Dialogfeld **Benutzerkonten** .</span><span class="sxs-lookup"><span data-stu-id="172b7-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="172b7-190">Schließen Sie das Dialogfeld andere **Benutzerkonten** .</span><span class="sxs-lookup"><span data-stu-id="172b7-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="172b7-191">Klicken Sie im Dialogfeld **Eigenschaften von Service Model Samples** auf der Registerkarte **Sicherheit** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="172b7-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="172b7-192">Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein, und fügen Sie dann den Namen des Internet Benutzerkontos ein, z. b\\. myMachineName% InternetGuestAccountName%.</span><span class="sxs-lookup"><span data-stu-id="172b7-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="172b7-193">Klicken Sie auf " **Namen überprüfen** ", um die Addition</span><span class="sxs-lookup"><span data-stu-id="172b7-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="172b7-194">Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="172b7-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="172b7-195">Überprüfen Sie für IIS 6,0 auch, ob Netzwerkdienst im Feld **Gruppen-oder Benutzernamen** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="172b7-196">Wenn NETZWERKDIENST nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="172b7-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="172b7-197">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="172b7-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="172b7-198">Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** den Namen des Computers ein, gefolgt von einem umgekehrten Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="172b7-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="172b7-199">Geben Sie **Dienst** nach dem umgekehrten Schrägstrich (ohne Leerzeichen) ein.</span><span class="sxs-lookup"><span data-stu-id="172b7-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="172b7-200">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="172b7-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="172b7-201">Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="172b7-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="172b7-202">Klicken Sie auf **OK** , um das Dialogfeld **Benutzer oder Gruppen auswählen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="172b7-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="172b7-203">Wenn Sie Windows XP SP2 mit IIS 5,1 verwenden, überprüfen Sie, ob im Feld **Gruppen-oder Benutzernamen** sowohl das Internet Gastkonto als auch das ASPNET aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="172b7-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="172b7-204">Beachten Sie, dass der ASPNET-Benutzer möglicherweise Mitglied der Sicherheitsgruppe "integrierte **Benutzer** " ist.</span><span class="sxs-lookup"><span data-stu-id="172b7-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="172b7-205">Wenn dies der Fall ist, müssen Sie, wenn die Gruppe " **Benutzer** " im Dialogfeld aufgeführt ist, Sie nicht als separates Element zur Liste zulässiger Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="172b7-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="172b7-206">So überprüfen Sie, ob ASPNET Teil der Sicherheitsgruppe " **Benutzer** " ist:</span><span class="sxs-lookup"><span data-stu-id="172b7-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="172b7-207">Klicken Sie im Startmenü auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="172b7-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="172b7-208">Klicken Sie auf das Symbol **Benutzerkonten** .</span><span class="sxs-lookup"><span data-stu-id="172b7-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="172b7-209">Überprüfen Sie in der Spalte **Gruppe** , ob der Wert für **ASPNET** "Users" lautet.</span><span class="sxs-lookup"><span data-stu-id="172b7-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172b7-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="172b7-210">See also</span></span>

- [<span data-ttu-id="172b7-211">Hostinganweisungen des Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="172b7-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
