---
title: Firewall-Anweisungen
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 343fa695039f6767f6ab33daa4e3cc51e8db5e47
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899639"
---
# <a name="firewall-instructions"></a><span data-ttu-id="cf643-102">Firewallanweisungen</span><span class="sxs-lookup"><span data-stu-id="cf643-102">Firewall instructions</span></span>

<span data-ttu-id="cf643-103">Sie müssen mehrere Ports oder Programme in der Firewall aktivieren, damit die Windows Communication Foundation (WCF)-Beispiele funktionieren können.</span><span class="sxs-lookup"><span data-stu-id="cf643-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="cf643-104">In vielen der Beispiele findet die Kommunikation über die Ports im Bereich 8000-8003 und über Port 9000 statt.</span><span class="sxs-lookup"><span data-stu-id="cf643-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="cf643-105">Die Firewall ist standardmäßig aktiviert und verhindert den Zugriff auf diese Ports.</span><span class="sxs-lookup"><span data-stu-id="cf643-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="cf643-106">Um die Beispiele mit der Firewall verwenden zu können, haben Sie abhängig von Ihren Anforderungen und Ihrer Sicherheitsumgebung mehrere Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="cf643-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>

- <span data-ttu-id="cf643-107">Option 1: Sie können die Beispiele während der Ausführung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf643-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="cf643-108">Ändern Sie die Konfiguration der Firewall nicht, und beginnen Sie mit der Erstellung und Ausführung der Beispiele.</span><span class="sxs-lookup"><span data-stu-id="cf643-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="cf643-109">Wenn ein Beispiel ausgeführt wird, wird das Dialogfeld **Windows-Sicherheitswarnung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf643-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="cf643-110">Hier können Sie das betreffende Beispielprogramm einer Liste mit nicht gesperrten Programmen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf643-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="cf643-111">Möglicherweise müssen Sie das Beispiel neu starten.</span><span class="sxs-lookup"><span data-stu-id="cf643-111">With this procedure, you may have to then restart the sample.</span></span>

- <span data-ttu-id="cf643-112">Option 2: Sie können Beispielprogramme im Voraus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf643-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="cf643-113">Starten Sie das Applet **Windows-Firewall-Systemsteuerung** , und aktivieren Sie die Beispiel Programme, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf643-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="cf643-114">Sie müssen die Programme zunächst erstellen, sodass die ausführbaren Dateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cf643-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="cf643-115">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="cf643-115">You can find more detailed instructions in the following procedure.</span></span>

- <span data-ttu-id="cf643-116">Option 3: Sie können ein Portbereich im Voraus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf643-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="cf643-117">Starten Sie das Applet **Windows-Firewall-Systemsteuerung** , und aktivieren Sie die Ports 80, 443, 8000-8003 und 9000, die von den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf643-117">Start the **Windows Firewall Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="cf643-118">Ausführlichere Informationen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="cf643-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="cf643-119">Diese Option birgt ein höheres Sicherheitsrisiko als die anderen Optionen, da jedes beliebige Programm auf die Ports zugreifen kann, nicht nur die Beispielprogramme.</span><span class="sxs-lookup"><span data-stu-id="cf643-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>

<span data-ttu-id="cf643-120">Wenn Sie nicht sicher sind, verwenden Sie die erste Option.</span><span class="sxs-lookup"><span data-stu-id="cf643-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="cf643-121">Wenn Sie eine Firewall von einem anderen Anbieter ausführen, müssen Sie möglicherweise ähnliche Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf643-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf643-122">Die Änderung der Firewallkonfiguration hat Auswirkungen auf die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="cf643-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="cf643-123">Es wird empfohlen, sich die vorgenommenen Änderungen zu notieren, sodass Sie sie wieder rückgängig machen können, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="cf643-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>

## <a name="enable-samples-programs-in-advance"></a><span data-ttu-id="cf643-124">Beispiel Programme im Voraus aktivieren</span><span class="sxs-lookup"><span data-stu-id="cf643-124">Enable samples programs in advance</span></span>

1. <span data-ttu-id="cf643-125">Erstellen Sie das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cf643-125">Build the sample.</span></span>

2. <span data-ttu-id="cf643-126">Wählen Sie **Start** > **Ausführen**aus, und geben Sie `firewall.cpl`ein.</span><span class="sxs-lookup"><span data-stu-id="cf643-126">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="cf643-127">Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cf643-127">This opens the **Windows Firewall Control Panel** applet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf643-128">Sie müssen über die Berechtigung zum Ändern der Firewalleinstellungen verfügen, um Beispiele auszuführen, für die eine Kommunikation durch die Windows-Firewall erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cf643-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="cf643-129">Wenn einige Firewalleinstellungen nicht verfügbar sind und der Computer eine Verbindung mit einer Domäne hergestellt hat, kann der Systemadministrator diese Einstellungen über Gruppenrichtlinien steuern.</span><span class="sxs-lookup"><span data-stu-id="cf643-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>

3. <span data-ttu-id="cf643-130">Führen Sie einen der folgenden betriebsspezifischen Schritte aus, um ein Programm durch die Windows-Firewall zuzulassen:</span><span class="sxs-lookup"><span data-stu-id="cf643-130">Complete one of the following operating-specific steps to allow a program through the Windows Firewall:</span></span>

    - <span data-ttu-id="cf643-131">Klicken Sie unter Windows 7 oder Windows Server 2008 R2 auf **Programm oder Feature durch Windows-Firewall zulassen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-131">On Windows 7 or Windows Server 2008 R2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="cf643-132">Klicken Sie auf **Einstellungen ändern** , > **ein anderes Programm zuzulassen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-132">Click **Change Settings** > **Allow Another Program**.</span></span>

    - <span data-ttu-id="cf643-133">Klicken Sie unter Windows Vista oder Windows Server 2008 auf **Programm durch die Windows-Firewall zulassen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-133">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>

4. <span data-ttu-id="cf643-134">Klicken Sie auf der Registerkarte **Ausnahmen** auf **Programm hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-134">On the **Exceptions** tab, click **Add Program**.</span></span>

5. <span data-ttu-id="cf643-135">Klicken Sie auf die Schaltfläche **Durchsuchen** , und wählen Sie die ausführbare Datei des Beispiels, das Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf643-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>

6. <span data-ttu-id="cf643-136">Wiederholen Sie die Schritte 4 und 5, bis Sie die ausführbaren Dateien aller Beispiele hinzugefügt haben, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf643-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>

7. <span data-ttu-id="cf643-137">Klicken Sie auf **OK** , um das Applet Firewall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="cf643-137">Click **OK** to close the firewall applet.</span></span>

## <a name="enable-a-port-range-in-advance"></a><span data-ttu-id="cf643-138">Aktivieren Sie einen Port Bereich im voraus.</span><span class="sxs-lookup"><span data-stu-id="cf643-138">Enable a port range in advance</span></span>

1. <span data-ttu-id="cf643-139">Wählen Sie **Start** > **Ausführen**aus, und geben Sie `firewall.cpl`ein.</span><span class="sxs-lookup"><span data-stu-id="cf643-139">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="cf643-140">Dadurch wird das Applet **Windows-Firewall-Systemsteuerung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cf643-140">This opens the **Windows Firewall Control Panel** applet.</span></span>

2. <span data-ttu-id="cf643-141">Führen Sie unter Windows 7 oder bei Windows Server 2008 R2 folgende Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cf643-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>

    1. <span data-ttu-id="cf643-142">Klicken Sie in der linken Spalte des Fensters Windows-Firewall auf **Erweiterte Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="cf643-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>

    2. <span data-ttu-id="cf643-143">Klicken Sie in der linken Spalte auf **Eingehende Regeln** .</span><span class="sxs-lookup"><span data-stu-id="cf643-143">Click **Inbound Rules** in the left column.</span></span>

    3. <span data-ttu-id="cf643-144">Klicken Sie in der rechten Spalte auf **neue Regeln** .</span><span class="sxs-lookup"><span data-stu-id="cf643-144">Click **New Rules** in the right column.</span></span>

    4. <span data-ttu-id="cf643-145">Wählen Sie **Port** , und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="cf643-145">Select **Port** and click **next**.</span></span>

    5. <span data-ttu-id="cf643-146">Wählen Sie **TCP** aus, und geben Sie `8000, 8001, 8002, 8003, 9000, 80, 443` in das Feld **bestimmte lokale Ports** ein.</span><span class="sxs-lookup"><span data-stu-id="cf643-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>

    6. <span data-ttu-id="cf643-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cf643-147">Click **Next**.</span></span>

    7. <span data-ttu-id="cf643-148">Wählen Sie **Verbindung zulassen**aus, und klicken Sie auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="cf643-148">Select **Allow the connection**, and click **Next** .</span></span>

    8. <span data-ttu-id="cf643-149">Wählen Sie **Domäne** und **Privat**aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="cf643-149">Select **Domain** and **Private**, and click **Next**.</span></span>

    9. <span data-ttu-id="cf643-150">Benennen Sie diese Regel `WCF-WF 4.0 Samples`, und klicken Sie auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="cf643-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>

    10. <span data-ttu-id="cf643-151">Klicken Sie auf **ausgehende Regeln** und wiederholen Sie die Schritte c bis h.</span><span class="sxs-lookup"><span data-stu-id="cf643-151">Click **Outbound Rules** and repeat steps c to h.</span></span>

3. <span data-ttu-id="cf643-152">Führen Sie unter Windows Vista oder Windows Server 2008 die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cf643-152">On Windows Vista or Windows Server 2008, follow these steps.</span></span>

    1. <span data-ttu-id="cf643-153">Klicken Sie auf **Programm durch die Windows-Firewall kommunizieren lassen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-153">Click **Allow a program through Windows Firewall**.</span></span>

    2. <span data-ttu-id="cf643-154">Klicken Sie auf der Registerkarte **Ausnahmen** auf **Port hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cf643-154">On the **Exceptions** tab, click **Add Port**.</span></span>

    3. <span data-ttu-id="cf643-155">Geben Sie einen Namen ein, geben Sie 8000 als Portnummer ein, und wählen Sie die Option **TCP** aus.</span><span class="sxs-lookup"><span data-stu-id="cf643-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>

    4. <span data-ttu-id="cf643-156">Klicken Sie auf die Schaltfläche **Bereich ändern** , wählen Sie die Option **mein Netzwerk** (Subnetz) nur aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf643-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>

    5. <span data-ttu-id="cf643-157">Wiederholen Sie die Schritte b bis d für die Ports 8001, 8002, 8003, 9000, 80 und 443.</span><span class="sxs-lookup"><span data-stu-id="cf643-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>

4. <span data-ttu-id="cf643-158">Klicken Sie auf **OK** , um das Applet Firewall zu schließen.</span><span class="sxs-lookup"><span data-stu-id="cf643-158">Click **OK** to close the firewall applet.</span></span>

> [!NOTE]
> <span data-ttu-id="cf643-159">Machen Sie die konfigurierten Ausnahmen wieder rückgängig, wenn Sie die Arbeit mit den Beispielen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="cf643-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="cf643-160">Öffnen Sie hierzu das Applet **Windows-Firewall-Systemsteuerung** , und entfernen Sie alle Programme oder Port Einträge, die von den vorherigen Prozeduren hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="cf643-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
