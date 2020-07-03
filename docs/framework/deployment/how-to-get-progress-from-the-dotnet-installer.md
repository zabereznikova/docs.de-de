---
title: 'Vorgehensweise: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5'
description: Hier erfahren Sie, wie Sie den Status des Installationsprogramms für .NET 4.5 abrufen. Wenn Sie Apps für diese .NET-Version entwickeln, können Sie das .NET 4.5-Setup in das Setup Ihrer App einschließen (damit verketten).
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
ms.openlocfilehash: 501fcaa7636d586ddfff8606768d4639fdc010d7
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904259"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a><span data-ttu-id="c7f50-104">Vorgehensweise: Abrufen des Status vom Installationsprogramm für .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c7f50-104">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>

<span data-ttu-id="c7f50-105">Bei .NET Framework 4.5 handelt es sich um eine weitervertreibbare Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c7f50-105">The .NET Framework 4.5 is a redistributable runtime.</span></span> <span data-ttu-id="c7f50-106">Wenn Sie Apps für diese Version von .NET Framework entwickeln, können Sie das .NET Framework 4.5-Setup als Teil einer erforderlichen Komponente in das Setup Ihrer App einschließen (mit dem Setup verketten).</span><span class="sxs-lookup"><span data-stu-id="c7f50-106">If you develop apps for this version of the .NET Framework, you can include (chain) .NET Framework 4.5 setup as a prerequisite part of your app's setup.</span></span> <span data-ttu-id="c7f50-107">Für ein angepasstes oder einheitliches Setup können Sie festlegen, dass das .NET Framework 4.5-Setup automatisch gestartet und sein Status nachverfolgt werden soll, während der Setupstatus Ihrer App angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7f50-107">To present a customized or unified setup experience, you may want to silently launch .NET Framework 4.5 setup and track its progress while showing your app's setup progress.</span></span> <span data-ttu-id="c7f50-108">Das .NET Framework 4.5-Setup (das beobachtet werden kann) definiert mithilfe eines MMIO-Segments (Memory-Mapped IO) ein Protokoll für die Kommunikation mit Ihrem Setup (dem Monitor oder Chainer), um die automatische Nachverfolgung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-108">To enable silent tracking, .NET Framework 4.5 setup (which can be watched) defines a protocol by using a memory-mapped I/O (MMIO) segment to communicate with your setup (the watcher or chainer).</span></span> <span data-ttu-id="c7f50-109">Dieses Protokoll definiert ein Verfahren für einen Chainer zum Abrufen von Statusinformationen und ausführlichen Ergebnissen, zum Antworten auf Meldungen sowie zum Abrechen des .NET Framework 4.5-Setups.</span><span class="sxs-lookup"><span data-stu-id="c7f50-109">This protocol defines a way for a chainer to obtain progress information, get detailed results, respond to messages, and cancel the .NET Framework 4.5 setup.</span></span>

- <span data-ttu-id="c7f50-110">**Aufruf**.</span><span class="sxs-lookup"><span data-stu-id="c7f50-110">**Invocation**.</span></span> <span data-ttu-id="c7f50-111">Um das .NET Framework 4.5-Setup aufzurufen und Statusinformationen aus dem MMIO-Abschnitt zu empfangen, muss das Setupprogramm folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="c7f50-111">To call .NET Framework 4.5 setup and receive progress information from the MMIO section, your setup program must do the following:</span></span>

    1. <span data-ttu-id="c7f50-112">Aufrufen des weitervertreibbaren .NET Framework 4.5-Programms:</span><span class="sxs-lookup"><span data-stu-id="c7f50-112">Call the .NET Framework 4.5 redistributable program:</span></span>

        `dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name`

        <span data-ttu-id="c7f50-113">Dabei ist *Abschnittname* ein beliebiger Name, mit dem Sie die App identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c7f50-113">Where *section name* is any name you want to use to identify your app.</span></span> <span data-ttu-id="c7f50-114">Das .NET Framework-Setup liest und schreibt asynchron aus dem/in den MMIO-Abschnitt. Daher ist es möglicherweise hilfreich, während dieser Zeit Ereignisse und Meldungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7f50-114">.NET Framework setup reads and writes to the MMIO section asynchronously, so you might find it convenient to use events and messages during that time.</span></span> <span data-ttu-id="c7f50-115">Im Beispiel wird der .NET Framework-Setupvorgang von einem Konstruktor erstellt, der sowohl den MMIO-Abschnitt (`TheSectionName`) zuordnet als auch ein Ereignis (`TheEventName`) definiert.</span><span class="sxs-lookup"><span data-stu-id="c7f50-115">In the example, the .NET Framework setup process is created by a constructor that both allocates the MMIO section (`TheSectionName`) and defines an event (`TheEventName`):</span></span>

        ```cpp
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        <span data-ttu-id="c7f50-116">Ersetzen Sie diese Namen durch Namen, die für das Setupprogramm eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="c7f50-116">Please replace those names with names that are unique to your setup program.</span></span>

    2. <span data-ttu-id="c7f50-117">Lesen aus dem MMIO-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7f50-117">Read from the MMIO section.</span></span> <span data-ttu-id="c7f50-118">In .NET Framework 4.5 werden die Download- und Installationsvorgänge gleichzeitig ausgeführt: Während ein Teil von .NET Framework installiert wird, wird vielleicht ein weiterer Teil heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-118">In the .NET Framework 4.5, the download and installation operations are simultaneous: One part of the .NET Framework might be installing while another part is downloading.</span></span> <span data-ttu-id="c7f50-119">Als Ergebnis wird der Status als zwei Zahlen (`m_downloadSoFar` und `m_installSoFar`), die von 0 bis 255 zunehmen, an den MMIO-Abschnitt zurückgesendet (das heißt, in den Abschnitt geschrieben).</span><span class="sxs-lookup"><span data-stu-id="c7f50-119">As a result, progress is sent back (that is, written) to the MMIO section as two numbers (`m_downloadSoFar` and `m_installSoFar`) that increase from 0 to 255.</span></span> <span data-ttu-id="c7f50-120">Wenn 255 geschrieben wurde und .NET Framework beendet wird, ist die Installation abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-120">When 255 is written and the .NET Framework exits, the installation is complete.</span></span>

- <span data-ttu-id="c7f50-121">**Exitcodes**</span><span class="sxs-lookup"><span data-stu-id="c7f50-121">**Exit codes**.</span></span> <span data-ttu-id="c7f50-122">Die folgenden Exitcodes des Befehls zum Aufrufen des weitervertreibbaren .NET Framework 4.5-Programms geben Aufschluss darüber, ob das Setup erfolgreich abgeschlossen wurde:</span><span class="sxs-lookup"><span data-stu-id="c7f50-122">The following exit codes from the command to call the .NET Framework 4.5 redistributable program indicate whether setup has succeeded or failed:</span></span>

  - <span data-ttu-id="c7f50-123">0 - erfolgreich abgeschlossenes Setup.</span><span class="sxs-lookup"><span data-stu-id="c7f50-123">0 - Setup completed successfully.</span></span>

  - <span data-ttu-id="c7f50-124">3010 – Setup wurde erfolgreich abgeschlossen. Das System muss neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="c7f50-124">3010 – Setup completed successfully; a system restart is required.</span></span>

  - <span data-ttu-id="c7f50-125">1602 – Setup wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-125">1602 – Setup has been canceled.</span></span>

  - <span data-ttu-id="c7f50-126">Alle anderen Codes - in Setup sind Fehler aufgetreten; Details dazu finden Sie in den unter "%temp%" erstellten Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="c7f50-126">All other codes - Setup encountered errors; examine the log files created in %temp% for details.</span></span>

- <span data-ttu-id="c7f50-127">**Abbrechen des Setups**</span><span class="sxs-lookup"><span data-stu-id="c7f50-127">**Canceling setup**.</span></span> <span data-ttu-id="c7f50-128">Sie können Setup jederzeit abbrechen, indem Sie mit der `Abort`-Methode das `m_downloadAbort`-Flag und das `m_ installAbort`-Flag im MMIO-Abschnitt festlegen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-128">You can cancel setup at any time by using the `Abort` method to set the `m_downloadAbort` and `m_ installAbort` flags in the MMIO section.</span></span>

## <a name="chainer-sample"></a><span data-ttu-id="c7f50-129">Chainer-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7f50-129">Chainer Sample</span></span>

<span data-ttu-id="c7f50-130">Im Chainer-Beispiel wird das .NET Framework 4.5-Setup automatisch gestartet und nachverfolgt, während der Status angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7f50-130">The Chainer sample silently launches and tracks .NET Framework 4.5 setup while showing progress.</span></span> <span data-ttu-id="c7f50-131">Dieses Beispiel ähnelt dem Chainer-Beispiel für .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c7f50-131">This sample is similar to the Chainer sample provided for the .NET Framework 4.</span></span> <span data-ttu-id="c7f50-132">Jedoch werden außerdem Systemneustarts vermieden, indem das Meldungsfeld zum Schließen von .NET Framework 4-Apps verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="c7f50-132">However, in addition, it can avoid system restarts by processing the message box for closing .NET Framework 4 apps.</span></span> <span data-ttu-id="c7f50-133">Weitere Informationen zu diesem Meldungsfeld finden Sie unter [Reducing System Restarts During .NET Framework 4.5 Installations (Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen)](reducing-system-restarts.md).</span><span class="sxs-lookup"><span data-stu-id="c7f50-133">For information about this message box, see [Reducing System Restarts During .NET Framework 4.5 Installations](reducing-system-restarts.md).</span></span> <span data-ttu-id="c7f50-134">Sie können dieses Beispiel mit dem .NET Framework 4-Installationsprogramm verwenden. In diesem Szenario wird die Meldung einfach nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="c7f50-134">You can use this sample with the .NET Framework 4 installer; in that scenario, the message is simply not sent.</span></span>

> [!WARNING]
> <span data-ttu-id="c7f50-135">Sie müssen das Beispiel als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-135">You must run the example as an administrator.</span></span>

<span data-ttu-id="c7f50-136">Sie können die vollständige Visual Studio-Projektmappe für das [Chainer-Beispiel für .NET Framework 4.5](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) von der MSDN Samples Gallery herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-136">You can download the complete Visual Studio solution for the [.NET Framework 4.5 Chainer Sample](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) from the MSDN Samples Gallery.</span></span>

<span data-ttu-id="c7f50-137">In den folgenden Abschnitten werden die bedeutendsten Dateien in diesem Beispiel beschrieben: MMIOChainer.h, ChainingdotNet4.cpp und IProgressObserver.h.</span><span class="sxs-lookup"><span data-stu-id="c7f50-137">The following sections describe the significant files in this sample: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h.</span></span>

#### <a name="mmiochainerh"></a><span data-ttu-id="c7f50-138">MMIOChainer.h</span><span class="sxs-lookup"><span data-stu-id="c7f50-138">MMIOChainer.h</span></span>

- <span data-ttu-id="c7f50-139">Die Datei „MMIOChainer.h“ (siehe den [vollständigen Code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) enthält die Datenstrukturdefinition und die Basisklasse, von der die chainer-Klasse abgeleitet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="c7f50-139">The MMIOChainer.h file (see [complete code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) contains the data structure definition and the base class from which the chainer class should be derived.</span></span> <span data-ttu-id="c7f50-140">.NET Framework 4.5 erweitert die MMIO-Datenstruktur, um Daten zu behandeln, die das .NET Framework 4.5-Installationsprogramm benötigt.</span><span class="sxs-lookup"><span data-stu-id="c7f50-140">The .NET Framework 4.5 extends the MMIO data structure to handle data that the .NET Framework 4.5 installer needs.</span></span> <span data-ttu-id="c7f50-141">Die Änderungen an der MMIO-Struktur sind abwärtskompatibel. Deshalb kann ein .NET Framework 4-Chainer mit dem .NET Framework 4.5-Setup verwendet werden, ohne dass eine Neukompilierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c7f50-141">The changes to the MMIO structure are backward-compatible, so a .NET Framework 4 chainer can work with .NET Framework 4.5 setup without requiring recompilation.</span></span> <span data-ttu-id="c7f50-142">In diesem Szenario wird jedoch nicht die Funktion zur Reduzierung von Systemneustarts unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7f50-142">However, this scenario does not support the feature for reducing system restarts.</span></span>

    <span data-ttu-id="c7f50-143">Ein Versionsfeld ermöglicht das Erkennen von Änderungen an der Struktur und dem Meldungsformat.</span><span class="sxs-lookup"><span data-stu-id="c7f50-143">A version field provides a means of identifying revisions to the structure and message format.</span></span> <span data-ttu-id="c7f50-144">Das .NET Framework-Setup bestimmt die Version der Chainer-Schnittstelle, indem die `VirtualQuery`-Funktion aufgerufen wird, um die Größe der Dateizuordnung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c7f50-144">The .NET Framework setup determines the version of the chainer interface by calling the `VirtualQuery` function to determine the size of the file mapping.</span></span> <span data-ttu-id="c7f50-145">Wenn die Größe für das Versionsfeld ausreicht, verwendet das .NET Framework-Setup den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="c7f50-145">If the size is large enough to accommodate the version field, .NET Framework setup uses the specified value.</span></span> <span data-ttu-id="c7f50-146">Wenn die Dateizuordnung zu klein ist, um ein Versionsfeld aufzunehmen, wie dies bei .NET Framework 4 der Fall ist, wird beim Setupvorgang Version 0 (4) angenommen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-146">If the file mapping is too small to contain a version field, which is the case with the .NET Framework 4, the setup process assumes version 0 (4).</span></span> <span data-ttu-id="c7f50-147">Wenn der Chainer die Version der Meldung, die vom .NET Framework-Setup gesendet werden soll, nicht unterstützt, geht das .NET Framework-Setup von der Antwort "Ignorieren" aus.</span><span class="sxs-lookup"><span data-stu-id="c7f50-147">If the chainer does not support the version of the message that .NET Framework setup wants to send, .NET Framework setup assumes an ignore response.</span></span>

    <span data-ttu-id="c7f50-148">Die MMIO-Datenstruktur ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="c7f50-148">The MMIO data structure is defined as follows:</span></span>

    ```cpp
    // MMIO data structure for interprocess communication
        struct MmioDataStructure
        {
            bool m_downloadFinished;               // Is download complete?
            bool m_installFinished;                // Is installation complete?
            bool m_downloadAbort;                  // Set to cause downloader to abort.
            bool m_installAbort;                   // Set to cause installer to abort.
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.
            HRESULT m_hrInternalError;
            WCHAR m_szCurrentItemStep[MAX_PATH];
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.

            BYTE m_version;                        // Version of the data structure, set by chainer:
                                                   // 0x0: .NET Framework 4
                                                   // 0x1: .NET Framework 4.5

            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.
        };
    ```

- <span data-ttu-id="c7f50-149">Die `MmioDataStructure`-Datenstruktur sollte nicht direkt verwendet werden. Verwenden Sie stattdessen die `MmioChainer`-Klasse zum Implementieren des Chainers.</span><span class="sxs-lookup"><span data-stu-id="c7f50-149">The `MmioDataStructure` data structure should not be used directly; use the `MmioChainer` class instead to implement your chainer.</span></span> <span data-ttu-id="c7f50-150">Verwenden Sie eine Ableitung von der Klasse `MmioChainer`, um die weitervertreibbare .NET Framework 4.5-Komponente zu verketten.</span><span class="sxs-lookup"><span data-stu-id="c7f50-150">Derive from the `MmioChainer` class to chain the .NET Framework 4.5 redistributable.</span></span>

#### <a name="iprogressobserverh"></a><span data-ttu-id="c7f50-151">IProgressObserver.h</span><span class="sxs-lookup"><span data-stu-id="c7f50-151">IProgressObserver.h</span></span>

- <span data-ttu-id="c7f50-152">Die Datei „IProgressObserver.h“ implementiert einen Statusbeobachter (siehe den [vollständigen Code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)).</span><span class="sxs-lookup"><span data-stu-id="c7f50-152">The IProgressObserver.h file implements a progress observer ([see complete code](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)).</span></span> <span data-ttu-id="c7f50-153">Dieser Beobachter wird über den Download- und Installationsstatus (als `char` ohne Vorzeichen mit den Werten 0-255, gibt Abschluss von 1 %-100 % an) benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="c7f50-153">This observer gets notified of download and installation progress (specified as an unsigned `char`, 0-255, indicating 1%-100% complete).</span></span> <span data-ttu-id="c7f50-154">Der Beobachter wird außerdem benachrichtigt, wenn der Chainee eine Meldung sendet, und der Beobachter sollte eine Antwort senden.</span><span class="sxs-lookup"><span data-stu-id="c7f50-154">The observer is also notified when the chainee sends a message, and the observer should send a response.</span></span>

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a><span data-ttu-id="c7f50-155">ChainingdotNet4.5.cpp</span><span class="sxs-lookup"><span data-stu-id="c7f50-155">ChainingdotNet4.5.cpp</span></span>

- <span data-ttu-id="c7f50-156">Die Datei [chainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) implementiert die von der `MmioChainer`-Klasse abgeleitete `Server`-Klasse und setzt die entsprechenden Methoden außer Kraft, um Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-156">The [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) file implements the `Server` class, which derives from the `MmioChainer` class and overrides the appropriate methods to display progress information.</span></span> <span data-ttu-id="c7f50-157">Der MmioChainer erstellt einen Abschnitt mit dem angegebenen Abschnittsnamen und initialisiert den Chainer mit dem angegebenen Ereignisnamen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-157">The MmioChainer creates a section with the specified section name and initializes the chainer with the specified event name.</span></span> <span data-ttu-id="c7f50-158">Der Ereignisname wird in der zugeordneten Datenstruktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7f50-158">The event name is saved in the mapped data structure.</span></span> <span data-ttu-id="c7f50-159">Sie sollten eindeutige Abschnitts- und Ereignisnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="c7f50-159">You should make the section and event names unique.</span></span> <span data-ttu-id="c7f50-160">Die `Server`-Klasse im folgenden Code startet das angegebene Setupprogramm, überwacht seinen Status und gibt einen Exitcode zurück.</span><span class="sxs-lookup"><span data-stu-id="c7f50-160">The `Server` class in the following code launches the specified setup program, monitors its progress, and returns an exit code.</span></span>

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    <span data-ttu-id="c7f50-161">Die Installation wird in der Main-Methode gestartet.</span><span class="sxs-lookup"><span data-stu-id="c7f50-161">The installation is started in the Main method.</span></span>

    ```cpp
    // Main entry point for program
    int __cdecl main(int argc, _In_count_(argc) char **_argv)
    {
        int result = 0;
        CString args;
        if (argc > 1)
        {
            args = CString(_argv[1]);
        }

        if (IsNetFx4Present(NETFX45_RC_REVISION))
        {
            printf(".NET Framework 4.5 is already installed");
        }
        else
        {
            result = Server().Launch(args);
        }

        return result;
    }
    ```

- <span data-ttu-id="c7f50-162">Vor dem Start der Installation überprüft der Chainer durch Aufrufen von `IsNetFx4Present`, ob .NET Framework 4.5 bereits installiert ist:</span><span class="sxs-lookup"><span data-stu-id="c7f50-162">Before launching the installation, the chainer checks to see if the .NET Framework 4.5 is already installed by calling `IsNetFx4Present`:</span></span>

    ```cpp
    ///  Checks for presence of the .NET Framework 4.
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.
    #define NETFX40_FULL_REVISION 0
    // TODO: Replace with released revision number
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5
    bool IsNetFx4Present(DWORD dwMinimumRelease)
    {
        DWORD dwError = ERROR_SUCCESS;
        HKEY hKey = NULL;
        DWORD dwData = 0;
        DWORD dwType = 0;
        DWORD dwSize = sizeof(dwData);

        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);
        if (ERROR_SUCCESS == dwError)
        {
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);

            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))
            {
                dwError = ERROR_INVALID_DATA;
            }
            else if (ERROR_FILE_NOT_FOUND == dwError)
            {
                // Release value was not found, let's check for 4.0.
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);

                // Install = (REG_DWORD)1;
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))
                {
                    // treat 4.0 as Release = 0
                    dwData = 0;
                }
                else
                {
                    dwError = ERROR_INVALID_DATA;
                }
            }
        }

        if (hKey != NULL)
        {
            ::RegCloseKey(hKey);
        }

        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));
    }
    ```

- <span data-ttu-id="c7f50-163">Sie können den Pfad der ausführbaren Datei (im Beispiel setup.exe) in der `Launch`-Methode ändern, damit sie auf den richtigen Speicherort zeigt, oder den Code anpassen, um den Speicherort zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-163">You can change the path of the executable (Setup.exe in the example) in the `Launch` method to point to its correct location, or customize the code to determine the location.</span></span> <span data-ttu-id="c7f50-164">Die `MmioChainer`-Basisklasse stellt die `Run()`-Blockierungsmethode bereit, die von der abgeleiteten Klasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c7f50-164">The `MmioChainer` base class provides a blocking `Run()` method that the derived class calls.</span></span>

    ```cpp
    bool Launch(const CString& args)
    {
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run
    STARTUPINFO si = {0};
    si.cb = sizeof(si);
    PROCESS_INFORMATION pi = {0};

    // Launch the Setup.exe that installs the .NET Framework 4.5
    BOOL bLaunchedSetup = ::CreateProcess(NULL,
     cmdline.GetBuffer(),
     NULL, NULL, FALSE, 0, NULL, NULL,
     &si,
     &pi);

    // If successful
    if (bLaunchedSetup != 0)
    {
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);
    Run(pi.hProcess, observer);

    ……………………..
    return (bLaunchedSetup != 0);
    }
    ```

- <span data-ttu-id="c7f50-165">Die `Send`-Methode fängt die Meldungen ab und verarbeitet sie.</span><span class="sxs-lookup"><span data-stu-id="c7f50-165">The `Send` method intercepts and processes the messages.</span></span> <span data-ttu-id="c7f50-166">In dieser Version von Microsoft .NET Framework wird nur die Meldung zum Schließen der Anwendung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7f50-166">In this version of the .NET Framework, the only supported message is the close application message.</span></span>

    ```cpp
            // SendMessage
            //
            // Send a message and wait for the response.
            // dwMessage: Message to send
            // pData: The buffer to copy the data to
            // dwDataLength: Initially a pointer to the size of pBuffer. Upon successful call, the number of bytes copied to pBuffer.
            //--------------------------------------------------------------
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)
        {
            DWORD dwResult = 0;
            printf("received message: %d\n", dwMessage);
            // Handle message
            switch (dwMessage)
            {
            case MMIO_CLOSE_APPS:
                {
                    printf("    applications are holding files in use:\n");
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)
                    {
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);
                    }

                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");
                    while (dwResult == 0)
                    {
                        switch (toupper(getwchar()))
                        {
                        case 'Y':
                            dwResult = IDYES;  // Close apps
                            break;
                        case 'N':
                            dwResult = IDNO;
                            break;
                        case 'R':
                            dwResult = IDRETRY;
                            break;
                        }
                    }
                    printf("\n");
                    break;
                }
            default:
                break;
            }
            printf("  response: %d\n  ", dwResult);
            return dwResult;
        }
    };
    ```

- <span data-ttu-id="c7f50-167">Statusdaten sind Werte vom Typ `char` ohne Vorzeichen zwischen 0 (0 %) und 255 (100 %).</span><span class="sxs-lookup"><span data-stu-id="c7f50-167">Progress data is an unsigned `char` between 0 (0%) and 255 (100%).</span></span>

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- <span data-ttu-id="c7f50-168">Das HRESULT wird an die `Finished`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="c7f50-168">The HRESULT is passed to the `Finished` method.</span></span>

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="c7f50-169">Die weitervertreibbare .NET Framework 4.5-Komponente schreibt in der Regel zahlreiche Statusmeldungen sowie eine einzelne Meldung, die den Abschluss angibt (auf der Chainer-Seite).</span><span class="sxs-lookup"><span data-stu-id="c7f50-169">The .NET Framework 4.5 redistributable typically writes many progress messages and a single message that indicates completion (on the chainer side).</span></span> <span data-ttu-id="c7f50-170">Es liest außerdem asynchron und sucht nach `Abort`-Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="c7f50-170">It also reads asynchronously, looking for `Abort` records.</span></span> <span data-ttu-id="c7f50-171">Wenn es einen `Abort`-Datensatz empfängt, wird die Installation abgebrochen, und nach dem Abbruch der Installation und dem Rollback der Setupvorgänge wird ein abgeschlossener Datensatz geschrieben, der E_ABORT lautet.</span><span class="sxs-lookup"><span data-stu-id="c7f50-171">If it receives an `Abort` record, it cancels the installation, and writes a finished record with E_ABORT as its data after the installation has been aborted and setup operations have been rolled back.</span></span>

<span data-ttu-id="c7f50-172">Ein typischer Server erstellt einen zufälligen MMIO-Dateinamen, erstellt die Datei (wie im vorherigen Codebeispiel in `Server::CreateSection` gezeigt) und startet das verteilbare Programm mit der `CreateProcess`-Methode. Dabei wird der Pipename mit der Option `-pipe someFileSectionName` übergeben.</span><span class="sxs-lookup"><span data-stu-id="c7f50-172">A typical server creates a random MMIO file name, creates the file (as shown in the previous code example, in `Server::CreateSection`), and launches the redistributable by using the `CreateProcess` method and passing the pipe name with the `-pipe someFileSectionName` option.</span></span> <span data-ttu-id="c7f50-173">Der Server sollte Methoden für `OnProgress`, `Send` und `Finished` mit spezifischem Code für die Benutzeroberfläche der Anwendung implementieren.</span><span class="sxs-lookup"><span data-stu-id="c7f50-173">The server should implement `OnProgress`, `Send`, and `Finished` methods with application UI-specific code.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7f50-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7f50-174">See also</span></span>

- [<span data-ttu-id="c7f50-175">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="c7f50-175">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="c7f50-176">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c7f50-176">Deployment</span></span>](index.md)
