---
title: 'Vorgehensweise: Debuggen von Windows-Dienstanwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
ms.openlocfilehash: 860f2ae22eb6510dc1f1a454ae3e51ccb366078b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053622"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="2fce2-102">Vorgehensweise: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="2fce2-102">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="2fce2-103">Ein Dienst muss im Kontext des Dienststeuerelement-Managers und nicht innerhalb von Visual Studio ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-103">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="2fce2-104">Aus diesem Grund ist das Debuggen eines Dienstes nicht so einfach wie das Debuggen anderer Anwendungstypen in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2fce2-104">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="2fce2-105">Damit ein Dienst gedebuggt werden kann, muss er gestartet werden. Danach muss ein Debugger an den Prozess angehängt werden, in dem er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-105">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="2fce2-106">Anschließend kann die Anwendung mit allen Standarddebugfunktionen von Visual Studio gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-106">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="2fce2-107">Das Anhängen darf nur bei bekannten Prozessen durchgeführt werden. Außerdem müssen die Konsequenzen bekannt sein, wenn an den Prozess angehängt wird und dieser u. U. abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-107">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="2fce2-108">Wenn z. B. an den WinLogon-Prozess angehängt und anschließend das Debuggen beendet wird, hält das System an, weil es ohne WinLogon nicht lauffähig ist.</span><span class="sxs-lookup"><span data-stu-id="2fce2-108">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="2fce2-109">Ein Debugger kann nur an einen Dienst angehängt werden, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-109">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="2fce2-110">Durch den Vorgang des Anhängens wird die aktuelle Funktion des Diensts unterbrochen. Die Verarbeitung des Diensts wird nicht tatsächlich beendet oder angehalten.</span><span class="sxs-lookup"><span data-stu-id="2fce2-110">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="2fce2-111">Das bedeutet: Wenn mit dem Debuggen eines Diensts begonnen wird, während er ausgeführt wird, befindet er sich während des Debuggens technisch gesehen weiterhin im Status Gestartet. Die Verarbeitung ist jedoch unterbrochen worden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-111">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="2fce2-112">Nach dem Anhängen an den Prozess können Sie Haltepunkte einrichten und diese zum Debuggen des Codes verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-112">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="2fce2-113">Sobald Sie das zum Anhängen des Prozesses verwendete Dialogfeld verlassen haben, befinden Sie sich im Debugmodus.</span><span class="sxs-lookup"><span data-stu-id="2fce2-113">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="2fce2-114">Dann kann der Dienst mit dem Dienststeuerungs-Manager gestartet, beendet, angehalten und fortgesetzt werden, sodass die festgelegten Haltepunkte angesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-114">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="2fce2-115">Nach erfolgreichem Debuggen kann der Dummydienst entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-115">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="2fce2-116">Dieser Artikel umfasst das Debuggen eines Dienstes, der auf dem lokalen Computer ausgeführt wird, aber Sie können auch Windows-Dienste debuggen, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-116">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="2fce2-117">Weitere Informationen finden Sie unter [Remotedebuggen](/visualstudio/debugger/debug-installed-app-package).</span><span class="sxs-lookup"><span data-stu-id="2fce2-117">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fce2-118">Das Debuggen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode kann Schwierigkeiten bereiten, da vom Dienststeuerungs-Manager ein Limit von 30 Sekunden für alle Versuche erzwungen wird, einen Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="2fce2-118">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="2fce2-119">Weitere Informationen finden Sie unter [Problembehandlung: Debuggen von Windows-Diensten](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fce2-119">For more information, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="2fce2-120">Um aussagekräftige Informationen für das Debuggen zu erhalten, muss der Visual Studio-Debugger Symboldateien für die Binärdateien finden, die gerade gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-120">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="2fce2-121">Wenn Sie einen Dienst debuggen, den Sie in Visual Studio erstellt haben, befinden sich die Symboldateien (PDB-Dateien) in demselben Ordner wie die ausführbare Datei oder Bibliothek, und der Debugger lädt diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="2fce2-121">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="2fce2-122">Wenn Sie einen Dienst debuggen, den Sie erstellt haben, sollten Sie zuerst die Symbole für den Dienst suchen und sicherstellen, dass sie vom Debugger gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="2fce2-122">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="2fce2-123">Weitere Informationen finden Sie unter [Angeben von Symbol- und Quelldateien (PDB) im Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span><span class="sxs-lookup"><span data-stu-id="2fce2-123">See [Specify Symbol (.pdb) and Source Files in the Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span></span> <span data-ttu-id="2fce2-124">Wenn Sie einen Systemprozess debuggen oder Symbole für Systemaufrufe in Ihren Diensten haben möchten, sollten Sie die Microsoft-Symbolserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-124">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="2fce2-125">Weitere Informationen finden Sie unter [Debugging with Symbols(Debuggen mit Symbolen)](/windows/desktop/DxTechArts/debugging-with-symbols).</span><span class="sxs-lookup"><span data-stu-id="2fce2-125">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="2fce2-126">So debuggen Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="2fce2-126">To debug a service</span></span>  
  
1. <span data-ttu-id="2fce2-127">Erstellen Sie Ihren Dienst in der Debugkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2fce2-127">Build your service in the Debug configuration.</span></span>  
  
2. <span data-ttu-id="2fce2-128">Installieren Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2fce2-128">Install your service.</span></span> <span data-ttu-id="2fce2-129">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fce2-129">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
3. <span data-ttu-id="2fce2-130">Starten Sie den Dienst entweder mit dem **Dienststeuerungs-Manager**, mit dem **Server-Explorer** oder aus dem Code.</span><span class="sxs-lookup"><span data-stu-id="2fce2-130">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="2fce2-131">Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fce2-131">For more information, see [How to: Start Services](how-to-start-services.md).</span></span>  
  
4. <span data-ttu-id="2fce2-132">Starten Sie Visual Studio mit Administratorrechten, damit Sie die Systemprozesse zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="2fce2-132">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5. <span data-ttu-id="2fce2-133">(Optional) Klicken Sie in Visual Studio auf der Menüleiste auf **Extras** und **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="2fce2-133">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="2fce2-134">Wählen Sie im Dialogfeld **Optionen** die Optionen **Debuggen** und **Symbole** aus. Aktivieren Sie das Kontrollkästchen **Microsoft-Symbolserver**, und klicken Sie anschließend auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fce2-134">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6. <span data-ttu-id="2fce2-135">Wählen Sie auf der Menüleiste aus dem Menü **Debuggen** oder **Extras** die Option **An den Prozess anhängen** aus.</span><span class="sxs-lookup"><span data-stu-id="2fce2-135">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="2fce2-136">(Tastatur: STRG+ALT+P)</span><span class="sxs-lookup"><span data-stu-id="2fce2-136">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="2fce2-137">Das Dialogfeld **Prozesse** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fce2-137">The **Processes** dialog box appears.</span></span>  
  
7. <span data-ttu-id="2fce2-138">Aktivieren Sie das Kontrollkästchen **Prozesse aller Benutzer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fce2-138">Select the **Show processes from all users** check box.</span></span>  
  
8. <span data-ttu-id="2fce2-139">Wählen Sie im Abschnitt **Verfügbare Prozesse** den Prozess für den Dienst aus, und klicken Sie anschließend auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="2fce2-139">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="2fce2-140">Der Prozess weist den gleichen Namen wie die ausführbare Datei für den Dienst auf.</span><span class="sxs-lookup"><span data-stu-id="2fce2-140">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="2fce2-141">Das Dialogfeld **An den Prozess anhängen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fce2-141">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="2fce2-142">Wählen Sie die entsprechenden Optionen aus, und klicken Sie anschließend auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-142">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2fce2-143">Sie befinden sich jetzt im Debugmodus.</span><span class="sxs-lookup"><span data-stu-id="2fce2-143">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="2fce2-144">Legen Sie die Haltepunkte fest, die im Code verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-144">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="2fce2-145">Öffnen Sie den Dienststeuerungs-Manager und bearbeiten Sie den Dienst, indem Sie Befehle zum Beenden, Anhalten und Fortsetzen ausgeben, um die festgelegten Haltepunkte anzusteuern.</span><span class="sxs-lookup"><span data-stu-id="2fce2-145">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="2fce2-146">Weitere Informationen zum Ausführen des Dienststeuerungs-Managers finden Sie unter [Vorgehensweise: Starten von Diensten](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fce2-146">For more information about running the Services Control Manager, see [How to: Start Services](how-to-start-services.md).</span></span> <span data-ttu-id="2fce2-147">Zudem finden Sie Informationen unter [Problembehandlung: Debuggen von Windows-Diensten](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fce2-147">Also, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="2fce2-148">Tipps zum Debuggen für Windows-Dienste</span><span class="sxs-lookup"><span data-stu-id="2fce2-148">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="2fce2-149">Durch das Anfügen an den Prozess des Dienstes können Sie die meisten, aber nicht alle, Codes für diesen Dienst debuggen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-149">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="2fce2-150">Z. B. weil der Dienst bereits gestartet wurde, können Sie den Code in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode des Dienstes oder den Code in der `Main`-Methode nicht debuggen, die verwendet wird, um den Dienst auf diese Weise zu lassen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-150">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="2fce2-151">Dies kann dadurch umgangen werden, dass ein zweiter temporärer Dienst in der Dienstanweisung erstellt wird, der lediglich als Hilfsmittel für das Debuggen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-151">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="2fce2-152">Beide Dienste können installiert werden. Anschließend wird der Dienstprozess geladen, indem der "Dummydienst" gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-152">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="2fce2-153">Sobald der Prozess vom temporären Dienst gestartet wurde, können Sie mit dem Anhängen an den Dienstprozess über das Menü **Debuggen** in Visual Studio beginnen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-153">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="2fce2-154">Versuchen Sie, Aufrufe an die <xref:System.Threading.Thread.Sleep%2A>-Methode zur Verzögerung der Aktion hinzuzufügen, bis Sie sie an den Prozess anfügen können.</span><span class="sxs-lookup"><span data-stu-id="2fce2-154">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="2fce2-155">Versuchen Sie, das Programm in eine reguläre Konsolenanwendung umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="2fce2-155">Try changing the program to a regular console application.</span></span> <span data-ttu-id="2fce2-156">Dazu schreiben Sie die `Main`-Methode wie folgt um, damit sie sowohl als Windows-Dienst als auch als Konsolenanwendung ausgeführt werden kann, je nachdem, wie sie gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2fce2-156">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="2fce2-157">Vorgehensweise: Ausführen eines Windows-Dienstes als Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="2fce2-157">How to: Run a Windows Service as a console application</span></span>  
  
1. <span data-ttu-id="2fce2-158">Fügen Sie eine Methode zu Ihrem Dienst hinzu, die die Methoden <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> ausführt:</span><span class="sxs-lookup"><span data-stu-id="2fce2-158">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. <span data-ttu-id="2fce2-159">Schreiben Sie die `Main`-Methode wie folgt um:</span><span class="sxs-lookup"><span data-stu-id="2fce2-159">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. <span data-ttu-id="2fce2-160">Legen Sie in der Registerkarte **Anwendung** der Projekteigenschaften den **Ausgabetyp** auf **Konsolenanwendung** fest.</span><span class="sxs-lookup"><span data-stu-id="2fce2-160">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4. <span data-ttu-id="2fce2-161">Wählen Sie **Debugging starten** (F5) aus.</span><span class="sxs-lookup"><span data-stu-id="2fce2-161">Choose **Start Debugging** (F5).</span></span>  
  
5. <span data-ttu-id="2fce2-162">Wenn Sie das Programm als Windows-Dienst ausführen, installieren Sie es, und starten Sie sie wie gewohnt für einen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="2fce2-162">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="2fce2-163">Es ist nicht notwendig, diese Änderungen rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="2fce2-163">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="2fce2-164">In einigen Fällen, z. B. beim Debuggen eines Problems, das nur beim Systemstart auftritt, müssen Sie den Windows-Debugger verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fce2-164">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="2fce2-165">[Laden Sie das Windows Driver Kit (WDK) herunter](/windows-hardware/drivers/download-the-wdk), und informieren Sie sich über die [Fehlerbehebung (Debugging) bei Windows-Diensten](https://support.microsoft.com/kb/824344).</span><span class="sxs-lookup"><span data-stu-id="2fce2-165">[Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) and see [How to debug Windows Services](https://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fce2-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fce2-166">See also</span></span>

- [<span data-ttu-id="2fce2-167">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="2fce2-167">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="2fce2-168">How to: Installieren und Deinstallieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="2fce2-168">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="2fce2-169">How to: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="2fce2-169">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="2fce2-170">Debugging a Service (Debuggen eines Diensts)</span><span class="sxs-lookup"><span data-stu-id="2fce2-170">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)
