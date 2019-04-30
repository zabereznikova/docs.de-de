---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: fdff88026a49989870ee5c47f9a38a65ecad3c80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007551"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="66cf9-102">Anleitung zum Einrichten eines virtuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="66cf9-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="66cf9-103">Die Windows Communication Foundation (WCF)-Beispiele dienen zum Freigeben von eines gemeinsamen virtuellen Verzeichnis mit dem Namen Servicemodelsamples, die das das dem Ordner %SystemDrive%\inetpub\wwwroot\servicemodelsamples zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66cf9-104">% SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="66cf9-105">Sie können die Dateien Setupvroot.bat und Cleanupvroot.bat aus ausführen, die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) zum Erstellen des virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="66cf9-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="66cf9-106">Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="66cf9-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="66cf9-107">Verfahren</span><span class="sxs-lookup"><span data-stu-id="66cf9-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="66cf9-108">So erstellen ein virtuelles Verzeichnis in IIS 7.0 oder 7.5</span><span class="sxs-lookup"><span data-stu-id="66cf9-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="66cf9-109">Von der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="66cf9-110">Klicken Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.</span><span class="sxs-lookup"><span data-stu-id="66cf9-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="66cf9-111">Mit der rechten Maustaste **Default Web Site**, und wählen Sie dann **Anwendung hinzufügen** zum Öffnen der **hinzufügen Anwendungsfenster**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="66cf9-112">Geben Sie im Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="66cf9-113">Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="66cf9-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="66cf9-114">Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="66cf9-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="66cf9-115">Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="66cf9-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="66cf9-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-116">Click **OK**.</span></span> <span data-ttu-id="66cf9-117">Die Webanwendung wird für die WCF-Beispiele erstellt.</span><span class="sxs-lookup"><span data-stu-id="66cf9-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66cf9-118">Diese Aufgabe muss nur einmal ausgeführt werden, da alle der WCF-Beispiele auf dem gleichen Namen Servicemodelsamples-Webanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="66cf9-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66cf9-119">In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.</span><span class="sxs-lookup"><span data-stu-id="66cf9-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="66cf9-120">Zusätzlich zum Erstellen des virtuellen Verzeichnisses, müssen Sie auch die Eigenschaften zum Aktivieren der WCF-Dienste zur Ausführung festlegen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="66cf9-121">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="66cf9-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="66cf9-122">So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0</span><span class="sxs-lookup"><span data-stu-id="66cf9-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="66cf9-123">Öffnen Sie ein Eingabeaufforderungsfenster und geben `start inetmgr` auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="66cf9-124">Klicken Sie im linken Bereich den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.</span><span class="sxs-lookup"><span data-stu-id="66cf9-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="66cf9-125">Mit der rechten Maustaste **Default Web Site** , und wählen Sie **neu, virtuelles Verzeichnis** zum Öffnen des Assistenten Erstellen eines virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="66cf9-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="66cf9-126">Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="66cf9-127">Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="66cf9-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="66cf9-128">Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="66cf9-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="66cf9-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="66cf9-130">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="66cf9-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="66cf9-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="66cf9-131">**Read**</span></span>  
  
    - <span data-ttu-id="66cf9-132">**Ausführen von Skripts (z. B. ASP)**</span><span class="sxs-lookup"><span data-stu-id="66cf9-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="66cf9-133">Klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen** um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66cf9-134">Diese Aufgabe muss nur einmal ausgeführt werden, da die WCF-Beispiele alle das gleiche virtuelle Verzeichnis Servicemodelsamples verwenden.</span><span class="sxs-lookup"><span data-stu-id="66cf9-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="66cf9-135">Um zusätzliche Eigenschaften virtueller Verzeichnisse in IIS 7.0 oder 7.5 festzulegen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="66cf9-136">Klicken Sie auf den Knoten servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="66cf9-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="66cf9-137">Unten im Fenster sind zwei Ansichten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="66cf9-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="66cf9-138">Wählen Sie **Ansicht "Features"** , wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="66cf9-139">Doppelklicken Sie auf den Eintrag für **Verzeichnissuche**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="66cf9-140">Wählen Sie im Aktionsbereich die **aktivieren** Option.</span><span class="sxs-lookup"><span data-stu-id="66cf9-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="66cf9-141">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="66cf9-142">Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="66cf9-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="66cf9-143">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="66cf9-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="66cf9-144">So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest</span><span class="sxs-lookup"><span data-stu-id="66cf9-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="66cf9-145">Mit der rechten Maustaste des Knotens Servicemodelsamples, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="66cf9-146">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="66cf9-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="66cf9-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="66cf9-147">**Read**</span></span>  
  
    - <span data-ttu-id="66cf9-148">**Besuche protokollieren**</span><span class="sxs-lookup"><span data-stu-id="66cf9-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="66cf9-149">**Ressource indizieren**</span><span class="sxs-lookup"><span data-stu-id="66cf9-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="66cf9-150">Wählen Sie die **Verzeichnissuche** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="66cf9-151">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="66cf9-152">So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7.0 oder 7.5 fest</span><span class="sxs-lookup"><span data-stu-id="66cf9-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="66cf9-153">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="66cf9-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="66cf9-154">Mit der rechten Maustaste in des Ordners Servicemodelsamples, und klicken Sie auf **Freigabe** oder **freigeben für**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="66cf9-155">Klicken Sie auf den Pfeil nach unten, links von der **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="66cf9-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="66cf9-156">Wählen Sie die **finden** Eintrag.</span><span class="sxs-lookup"><span data-stu-id="66cf9-156">Select the **Find** entry.</span></span> <span data-ttu-id="66cf9-157">Die **Benutzer oder Gruppen auswählen** Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="66cf9-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="66cf9-158">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="66cf9-159">Klicken Sie auf **Speicherorte**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-159">Click **Locations**.</span></span> <span data-ttu-id="66cf9-160">Die **Speicherorte** Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="66cf9-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="66cf9-161">Wählen Sie den Eintrag für den verwendeten Computer aus.</span><span class="sxs-lookup"><span data-stu-id="66cf9-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="66cf9-162">Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="66cf9-163">Nachdem Sie die Computer ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="66cf9-164">Klicken Sie auf **Jetzt suchen**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-164">Click **Find Now**.</span></span> <span data-ttu-id="66cf9-165">Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="66cf9-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="66cf9-166">Suchen der **IIS_IUSRS** Eintrag in der **Namen (Relative Distinguished Name)** Spalte.</span><span class="sxs-lookup"><span data-stu-id="66cf9-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="66cf9-167">Wählen Sie den Eintrag, und klicken Sie auf **OK** So schließen Sie die Suche die Ergebnisse im Fenster.</span><span class="sxs-lookup"><span data-stu-id="66cf9-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="66cf9-168">Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="66cf9-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="66cf9-169">Klicken Sie auf **Freigabe** , die Änderungen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="66cf9-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="66cf9-170">Nachdem die Änderungen zum Aktivieren der Freigabe abgeschlossen sind, klicken Sie auf **Fertig** schließen die **Dateifreigabe** Fenster.</span><span class="sxs-lookup"><span data-stu-id="66cf9-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="66cf9-171">So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein</span><span class="sxs-lookup"><span data-stu-id="66cf9-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="66cf9-172">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="66cf9-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="66cf9-173">Mit der rechten Maustaste die **Servicemodelsamples** Ordner, und klicken Sie dann auf **Freigabe und Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="66cf9-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="66cf9-174">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="66cf9-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="66cf9-175">Bei Verwendung von IIS 6.0 in der **Gruppen-oder Benutzernamen** Feld überprüfen, ob **Internetgastkonto** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="66cf9-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="66cf9-176">Falls der Eintrag nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="66cf9-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="66cf9-177">Klicken Sie auf **Start** und anschließend auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="66cf9-178">Wenn Sie nicht sehen die **Benutzerkonten** Symbol, klicken Sie auf **zur Kategorieansicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="66cf9-179">Klicken Sie auf die **Benutzerkonten** Symbol.</span><span class="sxs-lookup"><span data-stu-id="66cf9-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="66cf9-180">Klicken Sie unter ", oder wählen Sie ein Systemsteuerungssymbol" klicken Sie auf **Benutzerkonten**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="66cf9-181">In der **Benutzerkonten** Dialogfeld klicken Sie auf die **erweitert** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="66cf9-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="66cf9-182">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="66cf9-183">In der **lokale Benutzer und Gruppen** (Dialogfeld), klicken Sie zum Erweitern der **Benutzer** Ordner.</span><span class="sxs-lookup"><span data-stu-id="66cf9-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="66cf9-184">Doppelklicken Sie im rechten Bereich auf **Internetgastkonto**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="66cf9-185">In der **Eigenschaften** Dialogfeld Kopieren der Namen ein, die mit dem Internet-Gastkonto.</span><span class="sxs-lookup"><span data-stu-id="66cf9-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="66cf9-186">Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="66cf9-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="66cf9-187">Schließen der **Eigenschaften** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="66cf9-188">Schließen der **lokale Benutzer und Gruppen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="66cf9-189">Schließen der **Benutzerkonten** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="66cf9-190">Schließen Sie das andere **Benutzerkonten** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="66cf9-191">In der **Eigenschaften von Servicemodelsamples** Dialogfeld auf die **Sicherheit** auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="66cf9-192">Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich, und fügen Sie dann den Namen des Internetbenutzerkontos, z. B. MyMachineName\\InternetGuestAccountName %</span><span class="sxs-lookup"><span data-stu-id="66cf9-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="66cf9-193">Klicken Sie auf **Namen überprüfen** um den Namen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="66cf9-194">Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66cf9-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="66cf9-195">Für IIS 6.0 auch überprüfen, NETWORK SERVICE aufgeführt sein, die **Gruppen-oder Benutzernamen** Feld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="66cf9-196">Wenn NETZWERKDIENST nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="66cf9-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="66cf9-197">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="66cf9-198">In der **Benutzer oder Gruppen auswählen** im Dialogfeld Typ den Namen des Computers gefolgt von einem umgekehrten Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="66cf9-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="66cf9-199">Typ **Service** nach dem umgekehrten Schrägstrich (ohne Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="66cf9-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="66cf9-200">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="66cf9-201">Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="66cf9-202">Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="66cf9-203">Wenn Sie Windows XP SP2 mit IIS 5.1 verwenden, überprüfen Sie, dass sowohl Internetgastkonto und ASPNET vorhanden sind die **Gruppen-oder Benutzernamen** Feld.</span><span class="sxs-lookup"><span data-stu-id="66cf9-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="66cf9-204">Beachten Sie, dass der ASPNET-Benutzer ein Mitglied der integrierten möglicherweise **Benutzer** Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="66cf9-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="66cf9-205">Wenn dies der Fall ist, dann, wenn die **Benutzer** Gruppe, die im Dialogfeld aufgelistet ist, Sie müssen nicht als separates Element zur Liste der zugelassenen Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="66cf9-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="66cf9-206">Zum Überprüfen, ob ASPNET Teil ist die **Benutzer** Sicherheitsgruppe:</span><span class="sxs-lookup"><span data-stu-id="66cf9-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="66cf9-207">Auf der **starten** Menü klicken Sie auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="66cf9-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="66cf9-208">Klicken Sie auf die **Benutzerkonten** Symbol.</span><span class="sxs-lookup"><span data-stu-id="66cf9-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="66cf9-209">In der **Gruppe** Spalte überprüfen, ob der Wert für **ASPNET** ist "Benutzer".</span><span class="sxs-lookup"><span data-stu-id="66cf9-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66cf9-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66cf9-210">See also</span></span>

- [<span data-ttu-id="66cf9-211">Hostinganweisungen des Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="66cf9-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
