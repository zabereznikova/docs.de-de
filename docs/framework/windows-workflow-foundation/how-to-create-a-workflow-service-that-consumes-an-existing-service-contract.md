---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: c2ca9c349718c3939d74d052ff0ed448879cd045
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344714"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="99e78-102">Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="99e78-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="99e78-103">-Funktionen verbessern die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflowentwicklung.</span><span class="sxs-lookup"><span data-stu-id="99e78-103">features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="99e78-104">Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="99e78-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="99e78-105">Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="99e78-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99e78-106">Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts.</span><span class="sxs-lookup"><span data-stu-id="99e78-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="99e78-107">Weitere Informationen zum Entwickeln von Vertrag zuerst-Workflowdiensten finden Sie unter [Workflow Entwickeln von Vertrag zuerst](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="99e78-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="99e78-108">Erstellen des Workflowprojekts</span><span class="sxs-lookup"><span data-stu-id="99e78-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="99e78-109">Wählen Sie in Visual Studio **Datei**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="99e78-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="99e78-110">Wählen Sie die **WCF** unter den Knoten der **C#** Knoten in der **Vorlagen** Struktur, und wählen Sie die **WCF Workflow Service Application** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="99e78-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="99e78-111">Nennen Sie das neue Projekt `ContractFirst` , und klicken Sie auf **Ok**.</span><span class="sxs-lookup"><span data-stu-id="99e78-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="99e78-112">Erstellen des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="99e78-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="99e78-113">Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** .</span><span class="sxs-lookup"><span data-stu-id="99e78-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="99e78-114">Wählen Sie die **Code** Knoten auf der linken Seite, und die **Klasse** Vorlage auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="99e78-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="99e78-115">Nennen Sie die neue Klasse `IBookService` , und klicken Sie auf **Ok**.</span><span class="sxs-lookup"><span data-stu-id="99e78-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="99e78-116">Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="99e78-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="99e78-117">Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.</span><span class="sxs-lookup"><span data-stu-id="99e78-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4. <span data-ttu-id="99e78-118">Erstellen Sie das Projekt durch Drücken von **STRG + UMSCHALT + B**.</span><span class="sxs-lookup"><span data-stu-id="99e78-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="99e78-119">Importieren des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="99e78-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="99e78-120">Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und wählen Sie **Dienstvertrag importieren**.</span><span class="sxs-lookup"><span data-stu-id="99e78-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="99e78-121">Klicken Sie unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="99e78-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="99e78-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99e78-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="99e78-123">Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="99e78-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="99e78-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99e78-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="99e78-125">Erstellen Sie das Projekt durch Drücken von **STRG + UMSCHALT + B**, sodass die importierten Aktivitäten in der Toolbox angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="99e78-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="99e78-126">In **Projektmappen-Explorer**, Service1.xamlx zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="99e78-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="99e78-127">Der Workflowdienst wird im Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99e78-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="99e78-128">Wählen Sie die **Sequenz** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="99e78-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="99e78-129">Klicken Sie im Eigenschaftenfenster auf die **...**</span><span class="sxs-lookup"><span data-stu-id="99e78-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="99e78-130">Schaltfläche der **ImplementedContract** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="99e78-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="99e78-131">In der **Typauflistungs-Editor** Fenster, das angezeigt wird, klicken Sie auf die **Typ** Dropdown-Liste, und wählen Sie die **nach Typen suchen...**</span><span class="sxs-lookup"><span data-stu-id="99e78-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="99e78-132">Eintrag.</span><span class="sxs-lookup"><span data-stu-id="99e78-132">entry.</span></span> <span data-ttu-id="99e78-133">In der **durchsuchen, und wählen Sie einen .NET-Typ** Dialogfeld unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="99e78-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="99e78-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99e78-134">Click **OK**.</span></span> <span data-ttu-id="99e78-135">In der **Typauflistungs-Editor** Dialogfeld klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99e78-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="99e78-136">Wählen Sie aus, und löschen Sie die **ReceiveRequest** und **SendResponse** Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="99e78-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="99e78-137">Ziehen Sie aus der Toolbox ein **Buy_ReceiveAndSendReply** und **Checkout_Receive** Aktivität auf die **sequenzieller Dienst** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="99e78-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
