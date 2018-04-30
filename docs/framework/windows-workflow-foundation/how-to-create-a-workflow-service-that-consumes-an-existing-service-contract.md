---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7c28d8c2edbda5a42a290786b0ff40e3ab6dd5b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="ac946-102">Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="ac946-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="ac946-103">-Funktionen verbessern die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflowentwicklung.</span><span class="sxs-lookup"><span data-stu-id="ac946-103"> features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="ac946-104">Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="ac946-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="ac946-105">Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="ac946-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac946-106">Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts.</span><span class="sxs-lookup"><span data-stu-id="ac946-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="ac946-107">Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Service finden Sie unter [Vertrag zuerst-Workflowdienstentwicklung](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="ac946-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="ac946-108">Erstellen des Workflowprojekts</span><span class="sxs-lookup"><span data-stu-id="ac946-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="ac946-109">Wählen Sie in Visual Studio **Datei**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ac946-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="ac946-110">Wählen Sie die **WCF** unter den Knoten der **c#** Knoten in der **Vorlagen** Struktur, und wählen Sie die **WCF-Workflowdienstanwendung** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ac946-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="ac946-111">Nennen Sie das neue Projekt `ContractFirst` , und klicken Sie auf **Ok**.</span><span class="sxs-lookup"><span data-stu-id="ac946-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="ac946-112">Erstellen des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="ac946-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="ac946-113">Mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** .</span><span class="sxs-lookup"><span data-stu-id="ac946-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="ac946-114">Wählen Sie die **Code** Knoten auf der linken Seite und die **Klasse** Vorlage auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="ac946-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="ac946-115">Benennen Sie die neue Klasse `IBookService` , und klicken Sie auf **Ok**.</span><span class="sxs-lookup"><span data-stu-id="ac946-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="ac946-116">Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac946-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="ac946-117">Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.</span><span class="sxs-lookup"><span data-stu-id="ac946-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  <span data-ttu-id="ac946-118">Erstellen Sie das Projekt, indem Sie drücken **STRG + UMSCHALT + B**.</span><span class="sxs-lookup"><span data-stu-id="ac946-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="ac946-119">Importieren des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="ac946-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="ac946-120">Mit der rechten Maustaste des Projekts im **Projektmappen-Explorer** , und wählen Sie **Dienstvertrag importieren**.</span><span class="sxs-lookup"><span data-stu-id="ac946-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="ac946-121">Klicken Sie unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="ac946-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="ac946-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac946-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="ac946-123">Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ac946-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="ac946-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac946-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ac946-125">Erstellen Sie das Projekt, indem Sie drücken **STRG + UMSCHALT + B**, damit die importierten Aktivitäten in der Toolbox angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac946-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="ac946-126">In **Projektmappen-Explorer**, Service1.xamlx zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ac946-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="ac946-127">Der Workflowdienst wird im Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac946-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="ac946-128">Wählen Sie die **Sequenz** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ac946-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="ac946-129">Klicken Sie im Eigenschaftenfenster auf die **...**</span><span class="sxs-lookup"><span data-stu-id="ac946-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="ac946-130">die Schaltfläche in der **ImplementedContract** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ac946-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="ac946-131">In der **Typauflistungs-Editor** Fenster, das angezeigt wird, klicken Sie auf die **Typ** Dropdownliste, und wählen Sie die **nach Typen suchen...**</span><span class="sxs-lookup"><span data-stu-id="ac946-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="ac946-132">Eintrag.</span><span class="sxs-lookup"><span data-stu-id="ac946-132">entry.</span></span> <span data-ttu-id="ac946-133">In der **.NET-Typ suchen und auswählen** Dialogfeld unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="ac946-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="ac946-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac946-134">Click **OK**.</span></span> <span data-ttu-id="ac946-135">In der **Typauflistungs-Editor** Dialogfeld klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac946-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="ac946-136">Wählen Sie aus, und löschen Sie die **ReceiveRequest** und **SendResponse** Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="ac946-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="ac946-137">Ziehen Sie aus der Toolbox eine **Buy_ReceiveAndSendReply** und ein **Checkout_Receive** -Aktivität auf die **sequenzieller Dienst** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ac946-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
