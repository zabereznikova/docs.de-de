---
title: Hostinganweisungen des Internetinformationsdiensts
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 151c5ba8dd79e8554e7d79fb5b8182740b0be18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237689"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="ce1ad-102">Hostinganweisungen des Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="ce1ad-102">Internet Information Service Hosting Instructions</span></span>

<span data-ttu-id="ce1ad-103">Zum Ausführen der Beispiele, die vom Internetinformationsdienst (IIS) gehostet werden, müssen Sie sicherstellen, dass der IIS ordnungsgemäß installiert ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="ce1ad-104">So installieren Sie IIS Version 7.5 bei Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ce1ad-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="ce1ad-105">Wählen Sie unter **Server-Manager** die Option **Rollen aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="ce1ad-106">Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="ce1ad-107">Klicken Sie auf **weiter** , um das Dialogfeld **Server Rollen auswählen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="ce1ad-108">Wählen Sie in der Liste **Rollen** die Option **Anwendungs Server** aus, und klicken Sie dann zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Anwendungs Server Rolle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="ce1ad-109">Aktivieren Sie das Kontrollkästchen **Webserver (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="ce1ad-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="ce1ad-110">Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="ce1ad-111">Klicken Sie zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Rolle Webserver (IIS) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="ce1ad-112">Erweitern Sie den Knoten **Verwaltung**, und erweitern Sie dann Kompatibilität mit der **IIS 6-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="ce1ad-113">Wählen Sie **IIS 6-Skript Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="ce1ad-114">Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Rollen Dienste hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="ce1ad-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="ce1ad-116">Wenn die Zusammenfassung der Auswahl richtig ist, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="ce1ad-117">Wenn die Installation abgeschlossen ist, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="ce1ad-118">So installieren Sie IIS Version 7.5 unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="ce1ad-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="ce1ad-119">Klicken Sie auf **Start** und dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="ce1ad-120">Öffnen Sie die Gruppe " **Programme** ".</span><span class="sxs-lookup"><span data-stu-id="ce1ad-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="ce1ad-121">Klicken Sie unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="ce1ad-122">Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="ce1ad-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="ce1ad-124">Das Dialogfeld **Windows-Funktionen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="ce1ad-125">Erweitern Sie das Element mit der Bezeichnung **Internetinformationsdienste**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="ce1ad-126">Erweitern Sie das Element mit der Bezeichnung **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="ce1ad-127">Erweitern Sie das Element mit der Bezeichnung **Anwendungs Entwicklungsfunktionen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="ce1ad-128">Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:</span><span class="sxs-lookup"><span data-stu-id="ce1ad-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="ce1ad-129">**.NET-Erweiterbarkeit**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="ce1ad-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="ce1ad-131">**ISAPI-Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="ce1ad-132">**ISAPI-Filter**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="ce1ad-133">Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** die Option **Allgemeine HTTP-Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="ce1ad-134">Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="ce1ad-135">Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** den Knoten **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="ce1ad-136">Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="ce1ad-137">Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Webverwaltungs Tools**, und wählen Sie dann **IIS-Verwaltungskonsole** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="ce1ad-138">Erweitern Sie das Element mit der Bezeichnung **IIS 6-Verwaltungs Kompatibilität**, und wählen Sie dann **IIS 6-Skript Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="ce1ad-139">Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Microsoft .NET Framework 3.5.1**, und wählen Sie dann **Windows Communication Foundation http-Aktivierung** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="ce1ad-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="ce1ad-141">So installieren Sie IIS Version&#160;7.0 unter Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="ce1ad-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="ce1ad-142">Wählen Sie unter **Server-Manager** die Option **Rollen** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="ce1ad-143">Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="ce1ad-144">Klicken Sie auf **weiter** , um das Dialogfeld **Server Rollen auswählen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="ce1ad-145">Wählen Sie in der Liste **Rollen** die Option **Anwendungs Server** aus, und klicken Sie dann zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Anwendungs Server Rolle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="ce1ad-146">Aktivieren Sie das Kontrollkästchen **Webserver (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="ce1ad-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="ce1ad-147">Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="ce1ad-148">Klicken Sie zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Rolle Webserver (IIS) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="ce1ad-149">Erweitern Sie den Knoten **Verwaltung**, und erweitern Sie dann Kompatibilität mit der **IIS 6-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="ce1ad-150">Wählen Sie **IIS 6-Skript Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="ce1ad-151">Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Rollen Dienste hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="ce1ad-152">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="ce1ad-153">Wenn die Zusammenfassung der Auswahl richtig ist, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="ce1ad-154">Wenn die Installation abgeschlossen ist, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="ce1ad-155">So installieren Sie IIS Version&#160;7.0 unter Windows Vista</span><span class="sxs-lookup"><span data-stu-id="ce1ad-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="ce1ad-156">Klicken Sie auf Start und anschließend auf Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="ce1ad-157">Wählen Sie die Gruppe **Programme** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="ce1ad-158">Klicken Sie unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="ce1ad-159">Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="ce1ad-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="ce1ad-161">Das Dialogfeld **Windows-Funktionen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="ce1ad-162">Erweitern Sie das Element mit der Bezeichnung **Internetinformationsdienste**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="ce1ad-163">Erweitern Sie das Element mit der Bezeichnung **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="ce1ad-164">Erweitern Sie das Element mit der Bezeichnung **Anwendungs Entwicklungsfunktionen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="ce1ad-165">Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:</span><span class="sxs-lookup"><span data-stu-id="ce1ad-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="ce1ad-166">**.NET-Erweiterbarkeit**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="ce1ad-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="ce1ad-168">**ISAPI-Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="ce1ad-169">**ISAPI-Filter**</span><span class="sxs-lookup"><span data-stu-id="ce1ad-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="ce1ad-170">Erweitern Sie das Element mit der Bezeichnung **Webverwaltungs Tools**, und wählen Sie dann **IIS-Verwaltungskonsole** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="ce1ad-171">Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** die Option **Allgemeine HTTP-Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="ce1ad-172">Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="ce1ad-173">Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** den Knoten **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="ce1ad-174">Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="ce1ad-175">Erweitern Sie das Element mit der Bezeichnung **IIS 6-Verwaltungs Kompatibilität**, und wählen Sie dann **IIS 6-Skript Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="ce1ad-176">Erweitern Sie das Element mit der Bezeichnung **Microsoft .NET Framework 3,0**, und wählen Sie dann **Windows Communication Foundation http-Aktivierung** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="ce1ad-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="ce1ad-178">So installieren Sie IIS Version 6.0 unter Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ce1ad-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="ce1ad-179">Klicken Sie unter **Server verwalten** auf **Rolle hinzufügen oder entfernen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="ce1ad-180">Wählen Sie in der Liste **Server Rolle** die Option **Anwendungsserver (IIS, ASP.net)** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="ce1ad-181">Aktivieren Sie das Kontrollkästchen **aktivieren ASP.net** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="ce1ad-182">Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="ce1ad-183">So installieren Sie IIS Version 5.1 unter Windows XP mit installiertem Service Pack 2 und Service Pack 3</span><span class="sxs-lookup"><span data-stu-id="ce1ad-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="ce1ad-184">Klicken Sie in der Systemsteuerung auf **Software**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="ce1ad-185">Klicken Sie im Dialogfeld **Software** auf **Windows-Komponenten hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="ce1ad-186">Aktivieren Sie im **Assistenten für Windows-Komponenten** das Kontrollkästchen **Internetinformationsdienste (IIS)** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="ce1ad-187">Wenn das Dialogfeld **erforderliche Dateien** angezeigt wird, legen Sie die Installations-CD des Betriebssystems ein, navigieren Sie zum Ordner i386, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="ce1ad-188">Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig** stellen.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="ce1ad-189">Schließen Sie das Dialogfeld Software, und schließen **Sie** dann die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="ce1ad-190">So überprüfen Sie die Installation von IIS und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce1ad-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="ce1ad-191">Speichern Sie die HTML-Datei, die Sie am Ende dieses Themas finden, im Stammverzeichnis \InetPub\wwwroot unter dem Namen Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="ce1ad-192">Öffnen Sie ein Browserfenster.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="ce1ad-193">Geben `http://localhost/Default.aspx` Sie in das Feld Adresse ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="ce1ad-194">Es sollte eine Webseite mit dem Text "Hello World" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce1ad-195">Jedes Mal, wenn Sie eine neue Version der .NET Framework installieren, müssen Sie Aspnet_isapi als Webdienst Erweiterung für IIS erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="ce1ad-196">Dazu geben Sie den `aspnet_regiis –I –enable`-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ce1ad-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="ce1ad-197">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="ce1ad-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
