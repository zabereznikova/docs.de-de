---
title: Anleitung zum Einrichten eines virtuellen Verzeichnisses
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2684091d15a4c0796a0b8fb85952c0f902c1f545
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="c359d-102">Anleitung zum Einrichten eines virtuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="c359d-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="c359d-103">Für die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Beispiele ist die Nutzung eines gemeinsamen virtuellen Verzeichnisses mit dem Namen servicemodelsamples vorgesehen, das dem Ordner %SystemDrive%\inetpub\wwwroot\servicemodelsamples zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c359d-104">% SystemDrive% ist normalerweise C: oder D:, abhängig von dem Laufwerk, auf dem Internetinformationsdienste (IIS) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="c359d-105">Sie können die Dateien Setupvroot.bat und Cleanupvroot.bat aus ausführen, die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) beim Erstellen des virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="c359d-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="c359d-106">Wenn Sie es vorziehen, das virtuelle Verzeichnis manuell zu erstellen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="c359d-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c359d-107">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c359d-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="c359d-108">So erstellen Sie ein virtuelles Verzeichnis in IIS 7.0 oder 7.5</span><span class="sxs-lookup"><span data-stu-id="c359d-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="c359d-109">Aus der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c359d-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="c359d-110">Klicken Sie im linken Bereich, erweitern Sie den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Sites** Knoten.</span><span class="sxs-lookup"><span data-stu-id="c359d-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="c359d-111">Mit der rechten Maustaste **Default Web Site**, und wählen Sie dann **Anwendung hinzufügen** So öffnen die **hinzufügen Anwendungsfenster**.</span><span class="sxs-lookup"><span data-stu-id="c359d-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="c359d-112">Geben Sie im Fenster `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="c359d-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="c359d-113">Erstellen Sie das folgende Verzeichnis: %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="c359d-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="c359d-114">Legen Sie den physischen Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="c359d-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="c359d-115">Die meisten der WCF-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c359d-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="c359d-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c359d-116">Click **OK**.</span></span> <span data-ttu-id="c359d-117">Die Webanwendung wird für die WCF-Beispiele erstellt.</span><span class="sxs-lookup"><span data-stu-id="c359d-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c359d-118">Sie müssen diesen Vorgang nur einmal ausführen, da für alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiele dieselbe Webanwendung mit dem Namen servicemodelsamples verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c359d-118">This task must be performed only once, because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c359d-119">In dieser Dokumentation werden die Begriffe `virtual directory` und `Web application` als Synonyme behandelt.</span><span class="sxs-lookup"><span data-stu-id="c359d-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="c359d-120">Nachdem Sie das virtuelle Verzeichnis erstellt haben, müssen Sie die entsprechenden Eigenschaften einstellen, um das Ausführen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c359d-120">In addition to creating the virtual directory, you must also set its properties to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to run.</span></span> <span data-ttu-id="c359d-121">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="c359d-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="c359d-122">So erstellen Sie ein virtuelles Verzeichnis in IIS 5.1 oder 6.0</span><span class="sxs-lookup"><span data-stu-id="c359d-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="c359d-123">Öffnen Sie ein Eingabeaufforderungsfenster und geben `start inetmgr` auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c359d-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="c359d-124">Klicken Sie im linken Bereich, erweitern Sie den Knoten mit dem Namen des Computers, und erweitern Sie dann die **Websites** Knoten.</span><span class="sxs-lookup"><span data-stu-id="c359d-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="c359d-125">Mit der rechten Maustaste **Default Web Site** , und wählen Sie **neue virtuelle Verzeichnis** zum Öffnen des Assistenten Erstellen eines virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="c359d-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="c359d-126">Geben Sie im Assistenten `servicemodelsamples` als Alias für das virtuelle Verzeichnis, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="c359d-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="c359d-127">Legen Sie den Pfad auf %SystemDrive%\inetpub\wwwroot\servicemodelsamples fest.</span><span class="sxs-lookup"><span data-stu-id="c359d-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="c359d-128">Die meisten der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiele kopieren bei der Erstellung die ausführbaren Dateien der Dienste an diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c359d-128">Most of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="c359d-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c359d-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="c359d-130">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="c359d-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="c359d-131">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="c359d-131">**Read**</span></span>  
  
    -   <span data-ttu-id="c359d-132">**Ausführen von Skripts (z. B. ASP)**</span><span class="sxs-lookup"><span data-stu-id="c359d-132">**Run scripts (such as ASP)**</span></span>  
  
8.  <span data-ttu-id="c359d-133">Klicken Sie auf **Weiter**, und klicken Sie dann auf **Fertig stellen** um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c359d-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c359d-134">Sie müssen diesen Vorgang nur einmal ausführen, da für alle [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiele dasselbe virtuelle Verzeichnis mit dem Namen servicemodelsamples verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c359d-134">This task must be performed only once because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="c359d-135">Zum Festlegen von Eigenschaften der zusätzlich ein virtuelles Verzeichnis in IIS 7.0 oder 7.5</span><span class="sxs-lookup"><span data-stu-id="c359d-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="c359d-136">Klicken Sie auf den Knoten servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="c359d-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="c359d-137">Unten im Fenster sind zwei Ansichten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c359d-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="c359d-138">Wählen Sie **Ansicht "Features"** , wenn er nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="c359d-139">Doppelklicken Sie auf den Eintrag für **Verzeichnissuche**.</span><span class="sxs-lookup"><span data-stu-id="c359d-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="c359d-140">Wählen Sie im Aktionsbereich die **aktivieren** Option.</span><span class="sxs-lookup"><span data-stu-id="c359d-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="c359d-141">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="c359d-142">Zum Schluss müssen Sie die Sicherheitseigenschaften des Ordners servicemodelsamples so einstellen, dass andere darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c359d-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="c359d-143">Details finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="c359d-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="c359d-144">So legen Sie zusätzliche Eigenschaften für das virtuelle Verzeichnis in IIS 5.1 oder 6.0 fest</span><span class="sxs-lookup"><span data-stu-id="c359d-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="c359d-145">Mit der rechten Maustaste des Knotens Servicemodelsamples, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c359d-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c359d-146">Standardmäßig werden die folgenden Kontrollkästchen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="c359d-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="c359d-147">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="c359d-147">**Read**</span></span>  
  
    -   <span data-ttu-id="c359d-148">**Besuche protokollieren**</span><span class="sxs-lookup"><span data-stu-id="c359d-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="c359d-149">**Ressource indizieren**</span><span class="sxs-lookup"><span data-stu-id="c359d-149">**Index this resource**</span></span>  
  
3.  <span data-ttu-id="c359d-150">Wählen Sie die **Verzeichnissuche** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="c359d-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="c359d-151">So können Sie über Internet Explorer auf das Verzeichnis zugreifen, was beim Debuggen eines Diensts hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="c359d-152">So legen Sie die Sicherheitseigenschaften des Ordners in IIS 7.0 oder 7.5 fest</span><span class="sxs-lookup"><span data-stu-id="c359d-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="c359d-153">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="c359d-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="c359d-154">Mit der rechten Maustaste in des Ordners Servicemodelsamples, und klicken Sie auf **Freigabe** oder **freigeben für**.</span><span class="sxs-lookup"><span data-stu-id="c359d-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="c359d-155">Klicken Sie auf den Pfeil links neben der **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c359d-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="c359d-156">Wählen Sie die **suchen** Eintrag.</span><span class="sxs-lookup"><span data-stu-id="c359d-156">Select the **Find** entry.</span></span> <span data-ttu-id="c359d-157">Die **Benutzer oder Gruppen auswählen** Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c359d-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="c359d-158">Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="c359d-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="c359d-159">Klicken Sie auf **Speicherorte**.</span><span class="sxs-lookup"><span data-stu-id="c359d-159">Click **Locations**.</span></span> <span data-ttu-id="c359d-160">Die **Speicherorte** Fenster ist jetzt geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c359d-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="c359d-161">Wählen Sie den Eintrag für den verwendeten Computer aus.</span><span class="sxs-lookup"><span data-stu-id="c359d-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="c359d-162">Achten Sie darauf, den lokalen Computer und keinen Eintrag für Domänen oder Netzwerke auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c359d-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="c359d-163">Nachdem Sie die Computer ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c359d-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="c359d-164">Klicken Sie auf **Jetzt suchen**.</span><span class="sxs-lookup"><span data-stu-id="c359d-164">Click **Find Now**.</span></span> <span data-ttu-id="c359d-165">Als Suchergebnisse werden Objekte angezeigt, die mit dem lokalen Computer verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c359d-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="c359d-166">Suchen der **IIS_IUSRS** Eintrag in der **Namen (Relative Distinguished Name)** Spalte.</span><span class="sxs-lookup"><span data-stu-id="c359d-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="c359d-167">Wählen Sie diesen Eintrag, und klicken Sie auf **OK** Ergebnisfenster schließen die Suche.</span><span class="sxs-lookup"><span data-stu-id="c359d-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="c359d-168">Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c359d-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="c359d-169">Klicken Sie auf **Freigabe** damit die Änderungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c359d-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="c359d-170">Nachdem die Änderungen so aktivieren Sie die Freigabe abgeschlossen sind, klicken Sie auf **Fertig** schließen die **Dateifreigabe** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c359d-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="c359d-171">So stellen Sie die Sicherheitseigenschaften des Ordners in IIS 5.1 oder 6.0 ein</span><span class="sxs-lookup"><span data-stu-id="c359d-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="c359d-172">Navigieren Sie zu %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="c359d-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="c359d-173">Mit der rechten Maustaste die **Servicemodelsamples** Ordner, und klicken Sie dann auf **Freigabe und Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="c359d-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="c359d-174">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="c359d-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="c359d-175">Bei Verwendung von IIS 6.0, in der **Gruppen-oder Benutzernamen** Feld überprüfen, ob **Internetgastkonto** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="c359d-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="c359d-176">Falls der Eintrag nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="c359d-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="c359d-177">Klicken Sie auf **starten** , und klicken Sie dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c359d-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="c359d-178">Wenn Sie nicht sehen die **Benutzerkonten** Symbol, klicken Sie auf **zur Kategorieansicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="c359d-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="c359d-179">Klicken Sie auf die **Benutzerkonten** Symbol.</span><span class="sxs-lookup"><span data-stu-id="c359d-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="c359d-180">Klicken Sie unter ", oder wählen Sie ein Symbol" Systemsteuerung "," klicken Sie auf **Benutzerkonten**.</span><span class="sxs-lookup"><span data-stu-id="c359d-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="c359d-181">In der **Benutzerkonten** (Dialogfeld), klicken Sie auf die **erweitert** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="c359d-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="c359d-182">Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="c359d-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="c359d-183">In der **lokale Benutzer und Gruppen** (Dialogfeld), klicken Sie zum Erweitern der **Benutzer** Ordner.</span><span class="sxs-lookup"><span data-stu-id="c359d-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="c359d-184">Doppelklicken Sie im rechten Bereich auf **Internetgastkonto**.</span><span class="sxs-lookup"><span data-stu-id="c359d-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="c359d-185">In der **Eigenschaften** (Dialogfeld), die Kopie wird der Name als Internetgastkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="c359d-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="c359d-186">Standardmäßig beginnt der Name mit "USR_", gefolgt von dem Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="c359d-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="c359d-187">Schließen der **Eigenschaften** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c359d-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="c359d-188">Schließen der **lokale Benutzer und Gruppen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c359d-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="c359d-189">Schließen der **Benutzerkonten** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c359d-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="c359d-190">Schließen Sie das andere **Benutzerkonten** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c359d-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="c359d-191">In der **Eigenschaften von Servicemodelsamples** Dialogfeld auf die **Sicherheit** auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c359d-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="c359d-192">Geben Sie den Namen des Computers gefolgt von einem umgekehrten Schrägstrich ein, und fügen Sie den Namen des Internetbenutzerkontos, z. B. MyMachineName\\"% InternetGuestAccountName"</span><span class="sxs-lookup"><span data-stu-id="c359d-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="c359d-193">Klicken Sie auf **Namen überprüfen** um das Hinzufügen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c359d-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="c359d-194">Gültige Namen werden in Großbuchstaben und unterstrichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c359d-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="c359d-195">Für IIS 6.0 auch überprüfen Sie, ob Netzwerkdienst wird die **Gruppen-oder Benutzernamen** Feld.</span><span class="sxs-lookup"><span data-stu-id="c359d-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="c359d-196">Wenn NETZWERKDIENST nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="c359d-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="c359d-197">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c359d-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="c359d-198">In der **Benutzer oder Gruppen auswählen** Geben Sie im Dialogfeld der Namen des Computers einen umgekehrten Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="c359d-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="c359d-199">Typ **Service** nach dem umgekehrten Schrägstrich (ohne Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="c359d-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="c359d-200">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="c359d-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="c359d-201">Wenn mehrere Namen gefunden werden, wählen Sie **Netzwerkdienst** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c359d-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="c359d-202">Klicken Sie auf **OK** schließen die **Benutzer oder Gruppen auswählen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c359d-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="c359d-203">Wenn Sie Windows XP SP2 mit IIS 5.1 verwenden, überprüfen Sie, ob Internetgastkonto und ASPNET vorhanden sind die **Gruppen-oder Benutzernamen** Feld.</span><span class="sxs-lookup"><span data-stu-id="c359d-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="c359d-204">Beachten Sie, dass das ASPNET-Benutzer ein Mitglied der integrierten **Benutzer** Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="c359d-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="c359d-205">Wenn dies der Fall ist, dann wird bei der **Benutzer** Gruppe im Dialogfeld aufgeführt ist, müssen Sie nicht als separates Element der Liste der zugelassenen Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c359d-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="c359d-206">Zum Überprüfen, ob ASPNET Teil ist die **Benutzer** Sicherheitsgruppe:</span><span class="sxs-lookup"><span data-stu-id="c359d-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="c359d-207">Auf der **starten** Menü klicken Sie auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c359d-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="c359d-208">Klicken Sie auf die **Benutzerkonten** Symbol.</span><span class="sxs-lookup"><span data-stu-id="c359d-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="c359d-209">In der **Gruppe** Spalte, überprüfen Sie, ob der Wert für **ASPNET** ist "Benutzer".</span><span class="sxs-lookup"><span data-stu-id="c359d-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c359d-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c359d-210">See Also</span></span>  
 [<span data-ttu-id="c359d-211">Hostinganweisungen des Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="c359d-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
