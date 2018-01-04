---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c99748e77f1fccd9512c8915d0f4068d0da51a41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="cfcc6-102">Vorgehensweise: Erstellen eines Workflowdiensts zum Aufrufen eines anderen Workflowdiensts</span><span class="sxs-lookup"><span data-stu-id="cfcc6-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="cfcc6-103">Unter bestimmten Umständen ist es erforderlich, dass Informationen von Workflowdiensten von anderen Workflowdiensten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="cfcc6-104">In diesem Thema wird veranschaulicht, wie Sie einen Workflowdienst in einem anderen Workflowdienst aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="cfcc6-105">In diesem Thema werden zwei Workflowdienste erstellt: ein Workflowdienst mit einer Methode zur Umkehrung der Eingabezeichenfolge und ein Workflowdienst zur Konvertierung der umgekehrten Eingabezeichenfolge in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="cfcc6-106">So erstellen Sie den Reverser-Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="cfcc6-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="cfcc6-107">Führen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="cfcc6-108">Wählen Sie **Datei**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="cfcc6-109">Klicken Sie unter der **Workflow** Knoten in der **installierte Vorlagen** klicken Sie im Bereich **WCF-Workflowdienstanwendung**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="cfcc6-110">Nennen Sie die Projektmappe `NestedServices` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cfcc6-111">Klicken Sie unter **Server**, stellen Sie sicher, dass **lokalen IIS-Webserver verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="cfcc6-112">Klicken Sie auf **erstellt ein virtuelles Verzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="cfcc6-113">Klicken Sie auf **OK** in der Meldung, dass das virtuelle Verzeichnis wurde erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="cfcc6-114">Benennen Sie im Projektmappen-Explorer Service1.xamlx zu `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="cfcc6-115">Auf der **Projekteigenschaften** Seite für das neue Projekt, klicken Sie auf die **Web** Registerkarte. Legen Sie die **Startaktion** auf **bestimmte Seite**, und wählen Sie StringReverserService.xamlx als Startseite.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="cfcc6-116">Öffnen Sie StringReverserService.xamlx im Designer, löschen Sie die vorhandenen Aktivitäten `ReceiveRequest` und `SendReply`, und ziehen Sie eine `ReceiveAndSendReply`-Aktivität in die vorhandene Sequenzaktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="cfcc6-117">Legen Sie die **OperationName** auf reversestring fest.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="cfcc6-118">Legen Sie die **ServiceContractName** auf ireversestring fest.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="cfcc6-119">Wählen Sie die **CanCreateInstance** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="cfcc6-120">Wählen Sie die **SequentialService** Aktivität aus, und klicken Sie dann auf die **Variablen** Registerkarte am unteren Rand des Designers.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="cfcc6-121">Erstellen Sie zwei neue Variablen vom Typ String mit den Namen StringToReverse und ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="cfcc6-122">Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **Receive** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="cfcc6-123">Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen InputString vom Typ String, der StringToReverse zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="cfcc6-124">Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **SendReplyToReceive** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="cfcc6-125">Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen ReversedString vom Typ String, ReversedStringToReturn zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="cfcc6-126">Erstellen Sie im Projekt eine neue Klasse mit dem Namen StringLibrary, um die Logik für den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="cfcc6-127">Ersetzen Sie die Klassendefinition durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cfcc6-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="cfcc6-128">Um die ReverseString-Methode für die Eingabe aufzurufen, ziehen Sie ein **InvokeMethod** Aktivität aus der Toolbox auf den Abstand zwischen den **Receive** und **SendReply** Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="cfcc6-129">Legen Sie die Eigenschaften der Aktivität wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="cfcc6-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="cfcc6-130">**Methodenname**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="cfcc6-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="cfcc6-131">**Ergebnis**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="cfcc6-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="cfcc6-132">**Parameter**: Erstellen Sie einen neuen Parameter mit einem **Richtung** von In, eine **Typ** -Zeichenfolge, und ein **Wert** stringtoreverse.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="cfcc6-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="cfcc6-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="cfcc6-134">Testen Sie den Dienst durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-134">Test the service by pressing F5.</span></span> <span data-ttu-id="cfcc6-135">Doppelklicken Sie im angezeigten WCF-Testclient auf die ReverseString()-Methode.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="cfcc6-136">Geben Sie im Bereich Anforderung `Sample` für den Wert der InputString-Parameter.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="cfcc6-137">Klicken Sie auf **Aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-137">Click **Invoke**.</span></span> <span data-ttu-id="cfcc6-138">Die Rückgabe des Diensts sollte "elpmaS" lauten.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="cfcc6-139">So erstellen Sie den UpperCaser-Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="cfcc6-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="cfcc6-140">Mit der rechten Maustaste des NestedServices-Projekts, und wählen Sie **hinzufügen**, **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="cfcc6-141">In der **Workflow** Knoten **WCF-Workflowdienst**, und nennen Sie den neuen Dienst `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="cfcc6-142">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-142">Click **Add**.</span></span> <span data-ttu-id="cfcc6-143">Dadurch sollte dem Projekt der neue Workflowdienst UpperCaserService.xamlx hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="cfcc6-144">Öffnen Sie UpperCaserService.xamlx im Designer, und löschen Sie die vorhandene **ReceiveRequest** und `SendReply` Aktivitäten, und ziehen Sie eine `ReceiveAndSendReply` Aktivität in die vorhandene Sequenzaktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="cfcc6-145">Legen Sie die **OperationName** auf UppercaseString fest.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="cfcc6-146">Legen Sie die **ServiceContractName** auf iuppercasestring fest.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="cfcc6-147">Wählen Sie die **CanCreateInstance** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="cfcc6-148">Wählen Sie die Aktivität sequentialservice aus, und klicken Sie dann auf die **Variablen** Registerkarte am unteren Rand des Designers.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="cfcc6-149">Erstellen Sie drei neue Variablen vom Typ String mit den Namen StringToUpper, StringToReverse und StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="cfcc6-150">Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **Receive** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="cfcc6-151">Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen InputString vom Typ String, der StringToUpper zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="cfcc6-152">Klicken Sie auf die **definieren** wiederherstellungsverknüpfung in der **SendReplyToReceive** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="cfcc6-153">Klicken Sie auf die **Parameter**, und erstellen Sie einen Parameter mit dem Namen ModifiedString vom Typ String, StringToReturn zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="cfcc6-154">Erstellen Sie mit dem folgenden Code eine neue Methode in der StringLibrary-Klasse, um die Logik für den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="cfcc6-155">Um die UpperCaseString-Methode für die Eingabe aufzurufen, ziehen Sie ein **InvokeMethod** Aktivität aus der Toolbox auf den Abstand zwischen den **Receive** und **SendReply** Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="cfcc6-156">Legen Sie die Eigenschaften der Aktivität wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="cfcc6-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="cfcc6-157">**Methodenname**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="cfcc6-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="cfcc6-158">**Ergebnis**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="cfcc6-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="cfcc6-159">**Parameter**: Erstellen Sie einen neuen Parameter mit einem **Richtung** von In, eine **Typ** -Zeichenfolge, und ein **Wert** stringtoupper.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="cfcc6-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="cfcc6-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="cfcc6-161">Nun wird der erste Dienst für die geänderte Zeichenfolge aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="cfcc6-162">Mit der rechten Maustaste des Projekts, und wählen Sie **Hinzufügen eines Dienstverweises**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="cfcc6-163">Fügen Sie dem Dienst unter http://localhost/NestedServices/StringReverserService.xamlx einen Dienstverweis hinzu, und erstellen Sie das Projekt, um eine benutzerdefinierte Aktivität für den Zugriff auf den ersten Webdienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="cfcc6-164">Ziehen Sie eine Instanz der neuen Aktivität den Workflow zwischen den **InvokeMethod** Aktivität und die **SendReplyToReceive** Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="cfcc6-165">Weisen Sie der InputString-Eigenschaft der neuen Aktivität die StringToReverse-Variable zu, und weisen Sie der StringToReturn-Eigenschaft die StringToReturn-Variable zu.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="cfcc6-166">Öffnen Sie die Eigenschaftenseite des NestedServices-Projekts, und Ändern der **bestimmte Seite** in der **Web** Registerkarte in UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="cfcc6-167">Testen Sie den Dienst durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-167">Test the service by pressing F5.</span></span> <span data-ttu-id="cfcc6-168">Doppelklicken Sie im angezeigten WCF-Testclient auf die ReverseString()-Methode.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="cfcc6-169">Geben Sie im Bereich Anforderung `Sample` für den Wert der InputString-Parameter.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="cfcc6-170">Klicken Sie auf **Aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-170">Click **Invoke**.</span></span> <span data-ttu-id="cfcc6-171">Die Rückgabe des Diensts sollte "ELPMAS" lauten.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="cfcc6-172">So erstellen Sie einen Client, der die Dienste aufruft</span><span class="sxs-lookup"><span data-stu-id="cfcc6-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="cfcc6-173">Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen Client hinzu.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="cfcc6-174">Maustaste auf das Clientprojekt, und wählen Sie **Hinzufügen eines Dienstverweises**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="cfcc6-175">Klicken Sie im Fenster, das angezeigt wird, auf **Discover**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="cfcc6-176">Wählen Sie StringReverserService.xamlx aus, und geben Sie ReverseService als Namespace an.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="cfcc6-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfcc6-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="cfcc6-178">Ersetzen Sie die Main-Methode in der Datei Program.cs durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cfcc6-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
