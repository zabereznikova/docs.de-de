---
title: Hostinganweisungen des Internetinformationsdiensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de7dc897aa435d62c04c2e6a3ca82adf3a637a2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="f543c-102">Hostinganweisungen des Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="f543c-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="f543c-103">Zum Ausführen der Beispiele, die vom Internetinformationsdienst (IIS) gehostet werden, müssen Sie sicherstellen, dass der IIS ordnungsgemäß installiert ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f543c-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="f543c-104">So installieren Sie IIS Version 7.5 bei Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f543c-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="f543c-105">Von **Server-Manager**Option **Rollen.**</span><span class="sxs-lookup"><span data-stu-id="f543c-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="f543c-106">Klicken Sie unter **Rollenübersicht**, klicken Sie auf **Hinzufügen von Rollen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="f543c-107">Klicken Sie auf **Weiter** zum Anzeigen der **Serverrollen auswählen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="f543c-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="f543c-108">Wählen Sie **Anwendungsserver** aus der **Rollen** aus, und klicken Sie dann auf **Weiter** zweimal, um anzuzeigen die **Rollendienste auswählen** Dialogfeld für die Anwendungsserverrolle.</span><span class="sxs-lookup"><span data-stu-id="f543c-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="f543c-109">Wählen Sie die **Webserver (IIS)** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="f543c-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="f543c-110">Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="f543c-111">Klicken Sie auf **Weiter** zweimal, um die Anzeige der **Rollendienste auswählen** Dialogfeld für die Rolle "Webserver (IIS)".</span><span class="sxs-lookup"><span data-stu-id="f543c-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="f543c-112">Erweitern Sie **Verwaltungstools**, und erweitern Sie dann **IIS 6-Verwaltungskompatibilität**.</span><span class="sxs-lookup"><span data-stu-id="f543c-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="f543c-113">Wählen Sie **IIS 6-Skriptingtools**.</span><span class="sxs-lookup"><span data-stu-id="f543c-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="f543c-114">Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="f543c-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f543c-116">Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **installieren**.</span><span class="sxs-lookup"><span data-stu-id="f543c-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="f543c-117">Nach Abschluss der Installation klicken Sie auf **schließen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="f543c-118">So installieren Sie IIS Version 7.5 unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="f543c-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="f543c-119">Klicken Sie auf **starten**, und klicken Sie dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="f543c-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="f543c-120">Öffnen der **Programme** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f543c-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="f543c-121">Klicken Sie unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="f543c-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="f543c-122">Die **User Account Control** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f543c-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="f543c-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="f543c-124">Die **Windows-Features** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f543c-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="f543c-125">Erweitern Sie das Element namens **Internetinformationsdienste (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="f543c-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="f543c-126">Erweitern Sie das Element namens **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="f543c-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="f543c-127">Erweitern Sie das Element namens **Anwendungsentwicklungsfeatures**.</span><span class="sxs-lookup"><span data-stu-id="f543c-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="f543c-128">Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:</span><span class="sxs-lookup"><span data-stu-id="f543c-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="f543c-129">**NET-Erweiterbarkeit**</span><span class="sxs-lookup"><span data-stu-id="f543c-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="f543c-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="f543c-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="f543c-131">**ISAPI-Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="f543c-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="f543c-132">**ISAPI-Filter**</span><span class="sxs-lookup"><span data-stu-id="f543c-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="f543c-133">Unter dem Element namens **World Wide Web Services**, erweitern Sie **allgemeine HTTP-Features**.</span><span class="sxs-lookup"><span data-stu-id="f543c-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="f543c-134">Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f543c-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="f543c-135">Unter dem Element namens **World Wide Web Services**, erweitern Sie **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="f543c-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="f543c-136">Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f543c-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="f543c-137">Klicken Sie unter der **Internetinformationsdienste (IIS)** Verzeichnis ist, erweitern Sie das Element namens **Webverwaltungstools**, und wählen Sie dann **IIS-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="f543c-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="f543c-138">Erweitern Sie das Element namens **IIS 6-Verwaltungskompatibilität**, und wählen Sie dann **IIS 6-Skriptingtools**.</span><span class="sxs-lookup"><span data-stu-id="f543c-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="f543c-139">Klicken Sie unter der **Internetinformationsdienste (IIS)** Verzeichnis ist, erweitern Sie das Element namens **Microsoft .NET Framework 3.5.1**, und wählen Sie dann **Windows Communication Foundation-HTTP-Aktivierung**.</span><span class="sxs-lookup"><span data-stu-id="f543c-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="f543c-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="f543c-141">So installieren Sie IIS Version&#160;7.0 unter Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f543c-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="f543c-142">Von **Server-Manager**Option **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="f543c-143">Klicken Sie unter **Rollenübersicht**, klicken Sie auf **Hinzufügen von Rollen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="f543c-144">Klicken Sie auf **Weiter** zum Anzeigen der **Serverrollen auswählen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="f543c-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="f543c-145">Wählen Sie **Anwendungsserver** aus der **Rollen** aus, und klicken Sie dann auf **Weiter** zweimal, um anzuzeigen die **Rollendienste auswählen** Dialogfeld für die Anwendungsserverrolle.</span><span class="sxs-lookup"><span data-stu-id="f543c-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="f543c-146">Wählen Sie **Webserver (IIS)** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="f543c-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="f543c-147">Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="f543c-148">Klicken Sie auf **Weiter** zweimal, um die Anzeige der **Rollendienste auswählen** Dialogfeld für die Rolle "Webserver (IIS)".</span><span class="sxs-lookup"><span data-stu-id="f543c-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="f543c-149">Erweitern Sie **Verwaltungstools**, und erweitern Sie dann **IIS 6-Verwaltungskompatibilität**.</span><span class="sxs-lookup"><span data-stu-id="f543c-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="f543c-150">Wählen Sie **IIS 6-Skriptingtools**.</span><span class="sxs-lookup"><span data-stu-id="f543c-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="f543c-151">Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="f543c-152">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f543c-153">Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **installieren**.</span><span class="sxs-lookup"><span data-stu-id="f543c-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="f543c-154">Nach Abschluss der Installation klicken Sie auf **schließen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="f543c-155">So installieren Sie IIS Version&#160;7.0 unter Windows Vista</span><span class="sxs-lookup"><span data-stu-id="f543c-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="f543c-156">Klicken Sie auf Start und anschließend auf Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f543c-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="f543c-157">Wählen Sie die **Programme** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f543c-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="f543c-158">Klicken Sie unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="f543c-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="f543c-159">Die **User Account Control** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f543c-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="f543c-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="f543c-161">Die **Windows-Features** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f543c-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="f543c-162">Erweitern Sie das Element namens **Internetinformationsdienste (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="f543c-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="f543c-163">Erweitern Sie das Element namens **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="f543c-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="f543c-164">Erweitern Sie das Element namens **Anwendungsentwicklungsfeatures**.</span><span class="sxs-lookup"><span data-stu-id="f543c-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="f543c-165">Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:</span><span class="sxs-lookup"><span data-stu-id="f543c-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="f543c-166">**NET-Erweiterbarkeit**</span><span class="sxs-lookup"><span data-stu-id="f543c-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="f543c-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="f543c-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="f543c-168">**ISAPI-Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="f543c-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="f543c-169">**ISAPI-Filter**</span><span class="sxs-lookup"><span data-stu-id="f543c-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="f543c-170">Erweitern Sie das Element namens **Webverwaltungstools**, und wählen Sie dann **IIS-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="f543c-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="f543c-171">Unter dem Element namens **World Wide Web Services**, erweitern Sie **allgemeine HTTP-Features**.</span><span class="sxs-lookup"><span data-stu-id="f543c-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="f543c-172">Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f543c-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="f543c-173">Unter dem Element namens **World Wide Web Services**, erweitern Sie **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="f543c-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="f543c-174">Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f543c-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="f543c-175">Erweitern Sie das Element namens **IIS 6-Verwaltungskompatibilität**, und wählen Sie dann **IIS 6-Skriptingtools**.</span><span class="sxs-lookup"><span data-stu-id="f543c-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="f543c-176">Erweitern Sie das Element namens **Microsoft .NET Framework 3.0**, und wählen Sie dann **Windows Communication Foundation-HTTP-Aktivierung**.</span><span class="sxs-lookup"><span data-stu-id="f543c-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="f543c-177">Klicken Sie auf**OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-177">Click**OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="f543c-178">So installieren Sie IIS Version 6.0 unter Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="f543c-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="f543c-179">Von **Serververwaltung**, klicken Sie auf **hinzufügen oder Entfernen einer Rolle**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="f543c-180">Wählen Sie **Anwendungsserver (IIS, ASP.NET)** aus der **Serverrolle** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f543c-181">Wählen Sie **ASP.NET aktivieren** Kontrollkästchen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f543c-182">Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="f543c-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="f543c-183">So installieren Sie IIS Version 5.1 unter Windows XP mit installiertem Service Pack 2 und Service Pack 3</span><span class="sxs-lookup"><span data-stu-id="f543c-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="f543c-184">Klicken Sie in der Systemsteuerung auf **Software**.</span><span class="sxs-lookup"><span data-stu-id="f543c-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="f543c-185">In der **Software** (Dialogfeld), klicken Sie auf **Windows-Komponenten hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="f543c-186">In der **Assistenten für Windows-Komponenten**, wählen die **(Internet Information Services, IIS)** Kontrollkästchen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f543c-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f543c-187">Wenn die **benötigten Dateien** Dialogfeld wird angezeigt, fügen Sie den Betriebssystem-Installationsdatenträger, navigieren Sie zu dem Ordner "i386", und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f543c-188">Nach Abschluss der Installation klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="f543c-189">Schließen Sie die **Software** (Dialogfeld), und schließen Sie **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="f543c-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="f543c-190">So überprüfen Sie die Installation von IIS und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f543c-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="f543c-191">Speichern Sie die HTML-Datei, die Sie am Ende dieses Themas finden, im Stammverzeichnis \InetPub\wwwroot unter dem Namen Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="f543c-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="f543c-192">Öffnen Sie ein Browserfenster.</span><span class="sxs-lookup"><span data-stu-id="f543c-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="f543c-193">Typ `http://localhost/Default.aspx` in das Adressfeld ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f543c-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="f543c-194">Es sollte eine Webseite mit dem Text "Hello World" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f543c-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f543c-195">Jedes Mal, wenn Sie eine neue Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] installieren, müssen Sie aspnet_isapi erneut als Webdiensterweiterung für IIS registrieren.</span><span class="sxs-lookup"><span data-stu-id="f543c-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="f543c-196">Dazu geben Sie den `aspnet_regiis –I –enable`-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f543c-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="f543c-197">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="f543c-197">Sample Code</span></span>  
  
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
