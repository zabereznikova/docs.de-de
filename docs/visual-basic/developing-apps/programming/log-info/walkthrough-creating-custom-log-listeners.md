---
title: Erstellen von benutzerdefinierten Protokolllistenern (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bc6fde8dcbb27157f3fd180ad393bb406222195e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="6cee5-102">Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cee5-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="6cee5-103">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie einen benutzerdefinierten Protokolllistener erstellen und ihn so konfigurieren, dass er der Ausgabe des `My.Application.Log`-Objekts lauscht.</span><span class="sxs-lookup"><span data-stu-id="6cee5-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="6cee5-104">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="6cee5-104">Getting Started</span></span>  
 <span data-ttu-id="6cee5-105">Protokolllistener müssen von der <xref:System.Diagnostics.TraceListener>-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="6cee5-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
#### <a name="to-create-the-listener"></a><span data-ttu-id="6cee5-106">So erstellen Sie den Listener</span><span class="sxs-lookup"><span data-stu-id="6cee5-106">To create the listener</span></span>  
  
-   <span data-ttu-id="6cee5-107">Erstellen Sie in Ihrer Anwendung eine Klasse mit dem Namen `SimpleListener`, die von <xref:System.Diagnostics.TraceListener> erbt.</span><span class="sxs-lookup"><span data-stu-id="6cee5-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>  
  
     <span data-ttu-id="6cee5-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6cee5-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span></span>  
  
     <span data-ttu-id="6cee5-109">Die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> sind für die Basisklasse erforderlich und rufen `MsgBox` auf, um ihre Eingabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cee5-109">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>  
  
     <span data-ttu-id="6cee5-110">Das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut wird auf die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> angewendet, damit ihre Attribute den Methoden der Basisklasse entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6cee5-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="6cee5-111">Mithilfe des Attributs <xref:System.Security.Permissions.HostProtectionAttribute> kann der Host, der den Code ausführt, ermitteln, ob der Code die Synchronisierung der Hostsicherheit verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="6cee5-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6cee5-112">Das Attribut <xref:System.Security.Permissions.HostProtectionAttribute> ist nur in nicht verwalteten Anwendungen effektiv, die die Common Language Runtime hosten und Hostschutz implementieren, z.B. SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6cee5-112">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>  
  
 <span data-ttu-id="6cee5-113">Sie sollten der Assembly, die Ihren Protokolllistener enthält, einen starken Namen geben, um sicherzustellen, dass `My.Application.Log` Ihren Protokolllistener verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cee5-113">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>  
  
 <span data-ttu-id="6cee5-114">Im nächste Verfahren finden Sie einige einfache Schritte zum Erstellen einer Assembly mit starkem Namen und Protokolllistener.</span><span class="sxs-lookup"><span data-stu-id="6cee5-114">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="6cee5-115">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617).</span><span class="sxs-lookup"><span data-stu-id="6cee5-115">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617).</span></span>  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="6cee5-116">So geben Sie der Assembly mit Protokolllistener einen starken Namen</span><span class="sxs-lookup"><span data-stu-id="6cee5-116">To strongly name the log-listener assembly</span></span>  
  
1.  <span data-ttu-id="6cee5-117">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6cee5-118">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-118">On the **Project** menu, choose **Properties**.</span></span> <span data-ttu-id="6cee5-119">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="6cee5-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="6cee5-120">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-120">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="6cee5-121">Wählen Sie das Feld **Sign the assembly** (Assembly signieren) aus.</span><span class="sxs-lookup"><span data-stu-id="6cee5-121">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="6cee5-122">Wählen Sie in der Dropdownliste **Schlüsseldatei mit starkem Namen auswählen** **\<Neu>** aus.</span><span class="sxs-lookup"><span data-stu-id="6cee5-122">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>  
  
     <span data-ttu-id="6cee5-123">Das Dialogfeld **Schlüssel für einen starken Namen erstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6cee5-123">The **Create Strong Name Key** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="6cee5-124">Geben Sie einen Namen für die Schlüsseldatei im Feld **Schlüsseldateiname** ein.</span><span class="sxs-lookup"><span data-stu-id="6cee5-124">Provide a name for the key file in the **Key file name** box.</span></span>  
  
6.  <span data-ttu-id="6cee5-125">Geben Sie in die Felder **Kennwort eingeben** und **Kennwort bestätigen** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="6cee5-125">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>  
  
7.  <span data-ttu-id="6cee5-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-126">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="6cee5-127">Erstellen Sie die Anwendung neu.</span><span class="sxs-lookup"><span data-stu-id="6cee5-127">Rebuild the application.</span></span>  
  
## <a name="adding-the-listener"></a><span data-ttu-id="6cee5-128">Hinzufügen des Listeners</span><span class="sxs-lookup"><span data-stu-id="6cee5-128">Adding the Listener</span></span>  
 <span data-ttu-id="6cee5-129">Da die Assembly jetzt über einen starken Namen verfügt, müssen Sie den starken Namen des Listeners bestimmen, damit `My.Application.Log` Ihren Protokolllistener verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cee5-129">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>  
  
 <span data-ttu-id="6cee5-130">Das Format für einen Typ mit starkem Namen ist wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6cee5-130">The format of a strongly named type is as follows.</span></span>  
  
 <span data-ttu-id="6cee5-131">\<Typname>, \<Assemblyname>, \<Versionsnummer>, \<Kultur>, \<starker Name></span><span class="sxs-lookup"><span data-stu-id="6cee5-131">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="6cee5-132">So bestimmen Sie den starken Namen des Listeners</span><span class="sxs-lookup"><span data-stu-id="6cee5-132">To determine the strong name of the listener</span></span>  
  
-   <span data-ttu-id="6cee5-133">Im folgenden Code wird gezeigt, wie Sie den Namen für den Typ mit starkem Namen für `SimpleListener` bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6cee5-133">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>  
  
     <span data-ttu-id="6cee5-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="6cee5-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span></span>  
  
     <span data-ttu-id="6cee5-135">Der starke Name des Typs hängt von Ihrem Projekt ab.</span><span class="sxs-lookup"><span data-stu-id="6cee5-135">The strong name of the type depends on your project.</span></span>  
  
 <span data-ttu-id="6cee5-136">Sie können mit dem starken Namen den Listener zur `My.Application.Log`-Auflistung der Protokolllistener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cee5-136">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="6cee5-137">So fügen Sie den Listener zu „My.Application.Log“ hinzu</span><span class="sxs-lookup"><span data-stu-id="6cee5-137">To add the listener to My.Application.Log</span></span>  
  
1.  <span data-ttu-id="6cee5-138">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="6cee5-138">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="6cee5-139">- oder - </span><span class="sxs-lookup"><span data-stu-id="6cee5-139">-or-</span></span>  
  
     <span data-ttu-id="6cee5-140">Wenn eine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="6cee5-140">If there is an app.config file:</span></span>  
  
    1.  <span data-ttu-id="6cee5-141">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-141">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="6cee5-142">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="6cee5-142">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="6cee5-143">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6cee5-143">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="6cee5-144">Suchen Sie den `<listeners>` -Abschnitt, der sich im `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` befindet.</span><span class="sxs-lookup"><span data-stu-id="6cee5-144">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="6cee5-145">Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="6cee5-145">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="6cee5-146">Fügen Sie dem Abschnitt `<listeners>` dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="6cee5-146">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4.  <span data-ttu-id="6cee5-147">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="6cee5-147">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="6cee5-148">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="6cee5-148">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     <span data-ttu-id="6cee5-149">Ändern Sie den Wert von `SimpleLogStrongName` in den starken Namen des Listeners.</span><span class="sxs-lookup"><span data-stu-id="6cee5-149">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cee5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cee5-150">See Also</span></span>  
 <span data-ttu-id="6cee5-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6cee5-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="6cee5-152">[Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="6cee5-152">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="6cee5-153">[Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="6cee5-153">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="6cee5-154">[Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6cee5-154">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 [<span data-ttu-id="6cee5-155">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="6cee5-155">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

