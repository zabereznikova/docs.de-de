---
title: Erstellen eines AJAX-aktivierten WCF-Dienstanbieter und eines ASP.NET-Clients in Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 1f5c9eb1750b0df28836f147d5b4be1b223bb52e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053693"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="d8023-102">Vorgehensweise: Erstellen Sie einen AJAX-fähigen WCF-Dienst und einen ASP.NET-Client, der auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="d8023-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="d8023-103">In diesem Thema wird gezeigt, wie Sie mit Visual Studio einen AJAX-fähigen Windows Communication Foundation (WCF)-Dienst und einen ASP.NET-Client erstellen, der auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="d8023-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="d8023-104">Erstellen einer ASP.NET-Web-App</span><span class="sxs-lookup"><span data-stu-id="d8023-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="d8023-105">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8023-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="d8023-106">Wählen Sie im Menü **Datei** die Option **Neues** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="d8023-107">Erweitern Sie im Dialogfeld **Neues Projekt** die Kategorie**Visual C#**   >  **Web** ( **installiert** > ), und wählen Sie dann **ASP.NET-Webanwendung (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="d8023-108">Nennen Sie das **Projekt,** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8023-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="d8023-109">Wählen Sie im Dialogfeld **neue ASP.NET Webanwendung** die Option **leer** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8023-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Dialogfeld "ASP.net Web App type" in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="d8023-111">Webformular hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d8023-111">Add a web form</span></span>

1. <span data-ttu-id="d8023-112">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie**Neues Element** **Hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d8023-113">Erweitern Sie im Dialogfeld **Neues Element hinzufügen** die Kategorie **installierter** >   > **Visual C#**  **Web** , und wählen Sie dann die Vorlage **Web Form aus** .</span><span class="sxs-lookup"><span data-stu-id="d8023-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="d8023-114">Akzeptieren Sie den Standardnamen (**WebForm1**), und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="d8023-115">*WebForm1. aspx* wird in der **Quell** Ansicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8023-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="d8023-116">Fügen Sie das folgende Markup in den  **\<Text >** -Tags ein:</span><span class="sxs-lookup"><span data-stu-id="d8023-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="d8023-117">Erstellen eines AJAX-aktivierten WCF-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="d8023-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="d8023-118">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie**Neues Element** **Hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d8023-119">Erweitern Sie im Dialogfeld **Neues Element hinzufügen** die Kategorie **installierter** >   > **Visual C#**  **Web** , und wählen Sie dann die Vorlage **WCF-Dienst (AJAX-aktiviert)** aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Element Vorlage für den WCF-Dienst (Ajax-fähig) in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="d8023-121">Nennen Sie den Dienst " **CostService** ", und wählen Sie dann **Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d8023-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="d8023-122">*CostService.svc.cs* wird im Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8023-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="d8023-123">Implementieren Sie den-Vorgang im-Dienst.</span><span class="sxs-lookup"><span data-stu-id="d8023-123">Implement the operation in the service.</span></span> <span data-ttu-id="d8023-124">Fügen Sie der CostService-Klasse die folgende Methode hinzu, um die Kosten einer Menge von Sandwiches zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="d8023-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="d8023-125">Konfigurieren des Clients für den Zugriff auf den Dienst</span><span class="sxs-lookup"><span data-stu-id="d8023-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="d8023-126">Öffnen Sie die Datei *WebForm1. aspx* , und wählen Sie die **Entwurfs** Ansicht aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="d8023-127">Wählen Sie im Menü **Ansicht** die Option **Toolbox**aus.</span><span class="sxs-lookup"><span data-stu-id="d8023-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="d8023-128">Erweitern Sie den Knoten **AJAX-Erweiterungen** , und ziehen Sie **ScriptManager** per Drag & amp; Drop auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="d8023-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="d8023-129">Fügen Sie in der **Quell** Ansicht den folgenden Code zwischen den  **\<ScriptManager->** Tags hinzu, um den Pfad zum WCF-Dienst anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d8023-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="d8023-130">Fügen Sie den Code für die JavaScript `Calculate()`-Funktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8023-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="d8023-131">Platzieren Sie den folgenden Code im **Head** -Abschnitt des Webformulars:</span><span class="sxs-lookup"><span data-stu-id="d8023-131">Place the following code in the **head** section of the web form:</span></span>

    ```html
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="d8023-132">Dieser Code Ruft die-Methode von "CostService" auf, um den Preis für drei Sandwiches zu berechnen, und zeigt dann das Ergebnis in der Spanne mit dem Namen **additionresult**an.</span><span class="sxs-lookup"><span data-stu-id="d8023-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="d8023-133">Ausführen des Programms</span><span class="sxs-lookup"><span data-stu-id="d8023-133">Run the program</span></span>

<span data-ttu-id="d8023-134">Stellen Sie sicher, dass *WebForm1. aspx* den Fokus besitzt, und drücken Sie dann die Schaltfläche **Start** , um den WebClient zu starten.</span><span class="sxs-lookup"><span data-stu-id="d8023-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="d8023-135">Die Schaltfläche hat ein grünes Dreieck und sagt etwas wie **IIS Express (Microsoft Edge)** .</span><span class="sxs-lookup"><span data-stu-id="d8023-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="d8023-136">Alternativ können Sie **F5**drücken.</span><span class="sxs-lookup"><span data-stu-id="d8023-136">Or, you can press **F5**.</span></span> <span data-ttu-id="d8023-137">Klicken Sie auf den **Preis der drei Sandwiches** -Schaltfläche, um die erwartete Ausgabe von "3,75" zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d8023-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="d8023-138">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="d8023-138">Example code</span></span>

<span data-ttu-id="d8023-139">Im folgenden finden Sie den vollständigen Code in der Datei *CostService.svc.cs* :</span><span class="sxs-lookup"><span data-stu-id="d8023-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="d8023-140">Im folgenden finden Sie den vollständigen Inhalt der Seite " *WebForm1. aspx* ":</span><span class="sxs-lookup"><span data-stu-id="d8023-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
