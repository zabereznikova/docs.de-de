---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 05c59bde424049eb5bef8f8bd09c472b58eaa9ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248824"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="db828-102">Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="db828-102">How to: Create a workflow service that consumes an existing service contract</span></span>

<span data-ttu-id="db828-103">.NET Framework 4,5 bietet eine bessere Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflow Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="db828-103">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="db828-104">Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="db828-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="db828-105">Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="db828-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db828-106">Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts.</span><span class="sxs-lookup"><span data-stu-id="db828-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="db828-107">Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Diensten finden Sie unter [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="db828-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="db828-108">Erstellen des Workflowprojekts</span><span class="sxs-lookup"><span data-stu-id="db828-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="db828-109">Wählen Sie in Visual Studio **Datei** und **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="db828-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="db828-110">Wählen Sie in der **Vorlagen** Struktur unter dem Knoten **c#** den **WCF** -Knoten aus, und wählen Sie die Vorlage **WCF-Workflow Dienst Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="db828-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="db828-111">Benennen Sie das neue Projekt, `ContractFirst` und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="db828-112">Erstellen des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="db828-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="db828-113">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen**, **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="db828-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="db828-114">Wählen Sie den **Code** Knoten auf der linken Seite und die **Klassen** Vorlage auf der rechten Seite aus.</span><span class="sxs-lookup"><span data-stu-id="db828-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="db828-115">Benennen Sie die neue Klasse, `IBookService` und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="db828-116">Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="db828-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="db828-117">Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.</span><span class="sxs-lookup"><span data-stu-id="db828-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="db828-118">Erstellen Sie das Projekt, indem Sie **STRG + UMSCHALT + B** drücken.</span><span class="sxs-lookup"><span data-stu-id="db828-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="db828-119">Importieren des Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="db828-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="db828-120">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstvertrag importieren**.</span><span class="sxs-lookup"><span data-stu-id="db828-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="db828-121">**\<Current Project>** Öffnen Sie unter alle untergeordneten Knoten, und wählen Sie **ibookservice** aus.</span><span class="sxs-lookup"><span data-stu-id="db828-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="db828-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="db828-123">Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="db828-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="db828-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="db828-125">Erstellen Sie das Projekt, indem Sie **STRG + UMSCHALT + B** drücken, damit die importierten Aktivitäten in der Toolbox angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="db828-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="db828-126">Öffnen Sie in **Projektmappen-Explorer** die Datei Service1. xamlx.</span><span class="sxs-lookup"><span data-stu-id="db828-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="db828-127">Der Workflowdienst wird im Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db828-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="db828-128">Wählen Sie die **Sequence** -Aktivität aus.</span><span class="sxs-lookup"><span data-stu-id="db828-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="db828-129">Klicken Sie im Eigenschaftenfenster auf die **...**</span><span class="sxs-lookup"><span data-stu-id="db828-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="db828-130">-Schaltfläche in der **implementedContract** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db828-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="db828-131">Klicken Sie im angezeigten Fenster typauflistungs- **Editor** auf die Dropdown Liste **Typ** , und wählen Sie die Option **Typen suchen...**</span><span class="sxs-lookup"><span data-stu-id="db828-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="db828-132">.</span><span class="sxs-lookup"><span data-stu-id="db828-132">entry.</span></span> <span data-ttu-id="db828-133">Öffnen Sie im Dialogfeld **.NET-Typ suchen und auswählen** unter **\<Current Project>** alle untergeordneten Knoten, und wählen Sie **ibookservice** aus.</span><span class="sxs-lookup"><span data-stu-id="db828-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="db828-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-134">Click **OK**.</span></span> <span data-ttu-id="db828-135">Klicken Sie im Dialogfeld typauflistungs- **Editor** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="db828-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="db828-136">Wählen Sie die Aktivitäten **ReceiveRequest** und **SendResponse** aus, und löschen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="db828-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="db828-137">Ziehen Sie aus der Toolbox eine **Buy_ReceiveAndSendReply** und eine **Checkout_Receive** -Aktivität auf die Aktivität **sequenzieller Dienst** .</span><span class="sxs-lookup"><span data-stu-id="db828-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
