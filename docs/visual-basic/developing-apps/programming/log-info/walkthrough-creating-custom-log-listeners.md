---
title: Erstellen von benutzerdefinierten Protokolllistenern
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 5a140607a4fe7e1e13de54e8d56cab53e52aaa2a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398265"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="5478b-102">Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5478b-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="5478b-103">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie einen benutzerdefinierten Protokolllistener erstellen und ihn so konfigurieren, dass er der Ausgabe des `My.Application.Log`-Objekts lauscht.</span><span class="sxs-lookup"><span data-stu-id="5478b-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>

## <a name="getting-started"></a><span data-ttu-id="5478b-104">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="5478b-104">Getting Started</span></span>

<span data-ttu-id="5478b-105">Protokolllistener müssen von der <xref:System.Diagnostics.TraceListener>-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="5478b-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>

#### <a name="to-create-the-listener"></a><span data-ttu-id="5478b-106">So erstellen Sie den Listener</span><span class="sxs-lookup"><span data-stu-id="5478b-106">To create the listener</span></span>

- <span data-ttu-id="5478b-107">Erstellen Sie in Ihrer Anwendung eine Klasse mit dem Namen `SimpleListener`, die von <xref:System.Diagnostics.TraceListener> erbt.</span><span class="sxs-lookup"><span data-stu-id="5478b-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]

     <span data-ttu-id="5478b-108">Die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> sind für die Basisklasse erforderlich und rufen `MsgBox` auf, um ihre Eingabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5478b-108">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>

     <span data-ttu-id="5478b-109">Das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut wird auf die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> angewendet, damit ihre Attribute den Methoden der Basisklasse entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5478b-109">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="5478b-110">Mithilfe des Attributs <xref:System.Security.Permissions.HostProtectionAttribute> kann der Host, der den Code ausführt, ermitteln, ob der Code die Synchronisierung der Hostsicherheit verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="5478b-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5478b-111">Das Attribut <xref:System.Security.Permissions.HostProtectionAttribute> ist nur in nicht verwalteten Anwendungen effektiv, die die Common Language Runtime hosten und Hostschutz implementieren, z.B. SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5478b-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>

<span data-ttu-id="5478b-112">Sie sollten der Assembly, die Ihren Protokolllistener enthält, einen starken Namen geben, um sicherzustellen, dass `My.Application.Log` Ihren Protokolllistener verwendet.</span><span class="sxs-lookup"><span data-stu-id="5478b-112">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>

<span data-ttu-id="5478b-113">Im nächste Verfahren finden Sie einige einfache Schritte zum Erstellen einer Assembly mit starkem Namen und Protokolllistener.</span><span class="sxs-lookup"><span data-stu-id="5478b-113">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="5478b-114">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="5478b-114">For more information, see [Creating and Using Strong-Named Assemblies](../../../../standard/assembly/create-use-strong-named.md).</span></span>

#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="5478b-115">So geben Sie der Assembly mit Protokolllistener einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="5478b-115">To strongly name the log-listener assembly</span></span>

1. <span data-ttu-id="5478b-116">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5478b-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5478b-117">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5478b-117">On the **Project** menu, choose **Properties**.</span></span>

2. <span data-ttu-id="5478b-118">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="5478b-118">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="5478b-119">Wählen Sie das Feld **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5478b-119">Select the **Sign the assembly** box.</span></span>

4. <span data-ttu-id="5478b-120">Wählen Sie in der Dropdownliste **Schlüsseldatei mit starkem Namen auswählen** **\<New>** aus.</span><span class="sxs-lookup"><span data-stu-id="5478b-120">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>

     <span data-ttu-id="5478b-121">Das Dialogfeld **Schlüssel für einen starken Namen erstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5478b-121">The **Create Strong Name Key** dialog box opens.</span></span>

5. <span data-ttu-id="5478b-122">Geben Sie einen Namen für die Schlüsseldatei im Feld **Schlüsseldateiname** ein.</span><span class="sxs-lookup"><span data-stu-id="5478b-122">Provide a name for the key file in the **Key file name** box.</span></span>

6. <span data-ttu-id="5478b-123">Geben Sie in die Felder **Kennwort eingeben** und **Kennwort bestätigen** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="5478b-123">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>

7. <span data-ttu-id="5478b-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5478b-124">Click **OK**.</span></span>

8. <span data-ttu-id="5478b-125">Erstellen Sie die Anwendung neu.</span><span class="sxs-lookup"><span data-stu-id="5478b-125">Rebuild the application.</span></span>

## <a name="adding-the-listener"></a><span data-ttu-id="5478b-126">Hinzufügen des Listeners</span><span class="sxs-lookup"><span data-stu-id="5478b-126">Adding the Listener</span></span>

<span data-ttu-id="5478b-127">Da die Assembly jetzt über einen starken Namen verfügt, müssen Sie den starken Namen des Listeners bestimmen, damit `My.Application.Log` Ihren Protokolllistener verwendet.</span><span class="sxs-lookup"><span data-stu-id="5478b-127">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>

<span data-ttu-id="5478b-128">Das Format für einen Typ mit starkem Namen ist wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5478b-128">The format of a strongly named type is as follows.</span></span>

<span data-ttu-id="5478b-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span><span class="sxs-lookup"><span data-stu-id="5478b-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>

#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="5478b-130">So bestimmen Sie den starken Namen des Listeners</span><span class="sxs-lookup"><span data-stu-id="5478b-130">To determine the strong name of the listener</span></span>

- <span data-ttu-id="5478b-131">Im folgenden Code wird gezeigt, wie Sie den Namen für den Typ mit starkem Namen für `SimpleListener` bestimmen.</span><span class="sxs-lookup"><span data-stu-id="5478b-131">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]

     <span data-ttu-id="5478b-132">Der starke Name des Typs hängt von Ihrem Projekt ab.</span><span class="sxs-lookup"><span data-stu-id="5478b-132">The strong name of the type depends on your project.</span></span>

<span data-ttu-id="5478b-133">Sie können mit dem starken Namen den Listener zur `My.Application.Log`-Auflistung der Protokolllistener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5478b-133">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>

#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="5478b-134">So fügen Sie den Listener zu „My.Application.Log“ hinzu</span><span class="sxs-lookup"><span data-stu-id="5478b-134">To add the listener to My.Application.Log</span></span>

1. <span data-ttu-id="5478b-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="5478b-135">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="5478b-136">- oder -</span><span class="sxs-lookup"><span data-stu-id="5478b-136">-or-</span></span>

     <span data-ttu-id="5478b-137">Wenn eine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="5478b-137">If there is an app.config file:</span></span>

    1. <span data-ttu-id="5478b-138">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5478b-138">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="5478b-139">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="5478b-139">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="5478b-140">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5478b-140">Click **Add**.</span></span>

2. <span data-ttu-id="5478b-141">Suchen Sie den `<listeners>` -Abschnitt, der sich im `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` befindet.</span><span class="sxs-lookup"><span data-stu-id="5478b-141">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="5478b-142">Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="5478b-142">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="5478b-143">Fügen Sie dem Abschnitt `<listeners>` dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="5478b-143">Add this element to the `<listeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" />
    ```

4. <span data-ttu-id="5478b-144">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="5478b-144">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="5478b-145">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="5478b-145">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" type="SimpleLogStrongName" />
    ```

     <span data-ttu-id="5478b-146">Ändern Sie den Wert von `SimpleLogStrongName` in den starken Namen des Listeners.</span><span class="sxs-lookup"><span data-stu-id="5478b-146">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>

## <a name="see-also"></a><span data-ttu-id="5478b-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5478b-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="5478b-148">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="5478b-148">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="5478b-149">How to: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="5478b-149">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="5478b-150">How to: Schreiben von Protokollmeldungen</span><span class="sxs-lookup"><span data-stu-id="5478b-150">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="5478b-151">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="5478b-151">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
