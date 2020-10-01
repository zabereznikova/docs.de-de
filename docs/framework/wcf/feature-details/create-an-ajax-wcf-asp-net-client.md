---
title: Erstellen eines AJAX-aktivierten WCF-Dienstanbieter und eines ASP.NET-Clients in Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 0bfe55c68f68bfef7b7ec2034413b53d41b0c785
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609355"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="10273-102">Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift</span><span class="sxs-lookup"><span data-stu-id="10273-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="10273-103">In diesem Thema wird gezeigt, wie Sie mit Visual Studio einen AJAX-fähigen Windows Communication Foundation (WCF)-Dienst und einen ASP.NET-Client erstellen, der auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="10273-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="10273-104">Erstellen einer ASP.NET-Web-App</span><span class="sxs-lookup"><span data-stu-id="10273-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="10273-105">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="10273-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="10273-106">Wählen Sie im Menü **Datei** die Option **Neues**  >  **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="10273-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="10273-107">Erweitern Sie im Dialogfeld **Neues Projekt** die **Installed**  >  Kategorie**Visual c#**  >  -**webkategorie** , und wählen Sie dann **ASP.NET-Webanwendung (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="10273-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="10273-108">Nennen Sie das **Projekt,** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="10273-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="10273-109">Wählen Sie im Dialogfeld **neue ASP.NET Webanwendung** die Option **leer** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="10273-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Dialogfeld "ASP.net Web App type" in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="10273-111">Webformular hinzufügen</span><span class="sxs-lookup"><span data-stu-id="10273-111">Add a web form</span></span>

1. <span data-ttu-id="10273-112">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie **Add**  >  **Neues Element**hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="10273-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="10273-113">Erweitern Sie im Dialogfeld **Neues Element hinzufügen** **die**  >  Kategorie**Visual c#**  >  -**webkategorie** , und wählen Sie dann die **Web Form** -Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10273-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="10273-114">Akzeptieren Sie den Standardnamen (**WebForm1**), und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="10273-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="10273-115">*WebForm1. aspx* wird in der **Quell** Ansicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="10273-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="10273-116">Fügen Sie das folgende Markup innerhalb der **\<body>** Tags ein:</span><span class="sxs-lookup"><span data-stu-id="10273-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="10273-117">Erstellen eines AJAX-aktivierten WCF-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="10273-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="10273-118">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie **Add**  >  **Neues Element**hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="10273-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="10273-119">Erweitern Sie im Dialogfeld **Neues Element hinzufügen** **die**  >  **Visual c#**  >  -**webkategorie** , und wählen Sie dann die Vorlage **WCF-Dienst (AJAX-aktiviert)** aus.</span><span class="sxs-lookup"><span data-stu-id="10273-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Element Vorlage für den WCF-Dienst (Ajax-fähig) in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="10273-121">Nennen Sie den Dienst " **CostService** ", und wählen Sie dann **Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="10273-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="10273-122">*CostService.svc.cs* wird im Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="10273-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="10273-123">Implementieren Sie den-Vorgang im-Dienst.</span><span class="sxs-lookup"><span data-stu-id="10273-123">Implement the operation in the service.</span></span> <span data-ttu-id="10273-124">Fügen Sie der CostService-Klasse die folgende Methode hinzu, um die Kosten einer Menge von Sandwiches zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="10273-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="10273-125">Konfigurieren des Clients für den Zugriff auf den Dienst</span><span class="sxs-lookup"><span data-stu-id="10273-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="10273-126">Öffnen Sie die Datei *WebForm1. aspx* , und wählen Sie die **Entwurfs** Ansicht aus.</span><span class="sxs-lookup"><span data-stu-id="10273-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="10273-127">Wählen Sie im Menü **Ansicht** die Option **Toolbox**aus.</span><span class="sxs-lookup"><span data-stu-id="10273-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="10273-128">Erweitern Sie den Knoten **AJAX-Erweiterungen** , und ziehen Sie **ScriptManager** per Drag & amp; Drop auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="10273-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="10273-129">Fügen Sie in der **Quell** Ansicht den folgenden Code zwischen den- **\<ScriptManager>** Tags hinzu, um den Pfad zum WCF-Dienst anzugeben:</span><span class="sxs-lookup"><span data-stu-id="10273-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="10273-130">Fügen Sie den Code für die JavaScript-Funktion hinzu `Calculate()` .</span><span class="sxs-lookup"><span data-stu-id="10273-130">Add the code for the JavaScript function `Calculate()`.</span></span> <span data-ttu-id="10273-131">Platzieren Sie den folgenden Code im **Head** -Abschnitt des Webformulars:</span><span class="sxs-lookup"><span data-stu-id="10273-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="10273-132">Dieser Code Ruft die-Methode von "CostService" auf, um den Preis für drei Sandwiches zu berechnen, und zeigt dann das Ergebnis in der Spanne mit dem Namen **additionresult**an.</span><span class="sxs-lookup"><span data-stu-id="10273-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="10273-133">Ausführen des Programms</span><span class="sxs-lookup"><span data-stu-id="10273-133">Run the program</span></span>

<span data-ttu-id="10273-134">Stellen Sie sicher, dass *WebForm1. aspx* den Fokus besitzt, und drücken Sie dann die Schaltfläche **Start** , um den WebClient zu starten.</span><span class="sxs-lookup"><span data-stu-id="10273-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="10273-135">Die Schaltfläche hat ein grünes Dreieck und sagt etwas wie **IIS Express (Microsoft Edge)**.</span><span class="sxs-lookup"><span data-stu-id="10273-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="10273-136">Alternativ können Sie <kbd>F5</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="10273-136">Or, you can press <kbd>F5</kbd>.</span></span> <span data-ttu-id="10273-137">Klicken Sie auf den **Preis der drei Sandwiches** -Schaltfläche, um die erwartete Ausgabe von "3,75" zu generieren.</span><span class="sxs-lookup"><span data-stu-id="10273-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example"></a><span data-ttu-id="10273-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10273-138">Example</span></span>

<span data-ttu-id="10273-139">Im folgenden finden Sie den vollständigen Code in der Datei *CostService.svc.cs* :</span><span class="sxs-lookup"><span data-stu-id="10273-139">The following is the full code in the *CostService.svc.cs* file:</span></span>

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

<span data-ttu-id="10273-140">Im folgenden finden Sie den vollständigen Inhalt der Seite *WebForm1. aspx* :</span><span class="sxs-lookup"><span data-stu-id="10273-140">The following is the full contents of the *WebForm1.aspx* page:</span></span>

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
