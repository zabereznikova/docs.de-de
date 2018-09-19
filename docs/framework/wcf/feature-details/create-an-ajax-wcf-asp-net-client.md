---
title: Erstellen Sie in Visual Studio ein AJAX-aktivierten WCF-Dienst und einem ASP.NET-Client
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009309"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="86695-102">Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift</span><span class="sxs-lookup"><span data-stu-id="86695-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="86695-103">In diesem Thema wird gezeigt, wie mit Visual Studio zum Erstellen einer AJAX-fähigen Windows Communication Foundation (WCF)-Dienst und einem ASP.NET-Client, die auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="86695-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="86695-104">Erstellen einer ASP.NET-Web-App</span><span class="sxs-lookup"><span data-stu-id="86695-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="86695-105">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86695-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="86695-106">Von der **Datei** , wählen Sie im Menü **neu** > **Projekt**</span><span class="sxs-lookup"><span data-stu-id="86695-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="86695-107">In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie **ASP.NET-Webanwendung ((.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="86695-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="86695-108">Nennen Sie das Projekt **SandwichServices** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86695-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="86695-109">In der **neue ASP.NET-Webanwendung** wählen Sie im Dialogfeld **leere** und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="86695-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Dialogfeld für ASP.NET Web-app-Typ in Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="86695-111">Ein Web Form hinzufügen</span><span class="sxs-lookup"><span data-stu-id="86695-111">Add a web form</span></span>

1. <span data-ttu-id="86695-112">Mit der rechten Maustaste in des Projekts SandwichServices im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="86695-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="86695-113">In der **neues Element hinzufügen** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie die **Webformular** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="86695-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="86695-114">Übernehmen Sie den Standardnamen (**WebForm1**), und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86695-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="86695-115">*WebForm1.aspx* öffnet im **Quelle** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="86695-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="86695-116">Fügen Sie das folgende Markup innerhalb der  **\<Text >** Tags:</span><span class="sxs-lookup"><span data-stu-id="86695-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="86695-117">Erstellen eines AJAX-aktivierten WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="86695-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="86695-118">Mit der rechten Maustaste in des Projekts SandwichServices im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="86695-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="86695-119">In der **neues Element hinzufügen** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie die **WCF-Dienst (AJAX-fähig)** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="86695-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![WCF-Dienst (AJAX-fähig) Elementvorlage in Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="86695-121">Nennen Sie den Dienst **CostService** und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86695-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="86695-122">*CostService.svc.cs* im Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="86695-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="86695-123">Implementieren Sie den Vorgang im Dienst.</span><span class="sxs-lookup"><span data-stu-id="86695-123">Implement the operation in the service.</span></span> <span data-ttu-id="86695-124">Fügen Sie auf die Berechnung der Kosten für eine Menge Sandwiches CostService Klasse die folgende Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="86695-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="86695-125">Konfigurieren des Clients für den Zugriff auf den Dienst</span><span class="sxs-lookup"><span data-stu-id="86695-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="86695-126">Öffnen der *WebForm1.aspx* und wählen Sie die **Entwurf** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="86695-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="86695-127">Von der **Ansicht** , wählen Sie im Menü **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="86695-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="86695-128">Erweitern Sie die **AJAX-Erweiterungen** Knoten und Drag & Drop eine **ScriptManager** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="86695-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="86695-129">In der **Quelle** anzuzeigen, fügen Sie den folgenden Code zwischen den  **\<ScriptManager >** Tags aus, um den Pfad zum WCF-Dienst angeben:</span><span class="sxs-lookup"><span data-stu-id="86695-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. <span data-ttu-id="86695-130">Fügen Sie den Code für die Javascript-Funktion `Calculate()`.</span><span class="sxs-lookup"><span data-stu-id="86695-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="86695-131">Platzieren Sie den folgenden Code in die **Head** Abschnitt des Webformulars:</span><span class="sxs-lookup"><span data-stu-id="86695-131">Place the following code in the **head** section of the web form:</span></span>

    ```javascript
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

   <span data-ttu-id="86695-132">Dieser Code Ruft die Methode der CostService zum Berechnen des Preis für drei Sandwiches und zeigt dann das Ergebnis in der Spanne namens **AdditionResult**.</span><span class="sxs-lookup"><span data-stu-id="86695-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="86695-133">Ausführen des Programms</span><span class="sxs-lookup"><span data-stu-id="86695-133">Run the program</span></span>

<span data-ttu-id="86695-134">Stellen Sie sicher, dass *WebForm1.aspx* den Fokus besitzt, und drücken Sie dann die **starten** Schaltfläche, um den WebClient zu starten.</span><span class="sxs-lookup"><span data-stu-id="86695-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="86695-135">Die Schaltfläche wurde ein grünes Dreieck und etwa sagt **IIS Express (Microsoft Edge)**.</span><span class="sxs-lookup"><span data-stu-id="86695-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="86695-136">Sie können durch Drücken **F5**.</span><span class="sxs-lookup"><span data-stu-id="86695-136">Or, you can press **F5**.</span></span> <span data-ttu-id="86695-137">Klicken Sie auf die **Preis 3 Sandwiches** Schaltfläche, um die erwartete Ausgabe "3,75" zu generieren.</span><span class="sxs-lookup"><span data-stu-id="86695-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="86695-138">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="86695-138">Example code</span></span>

<span data-ttu-id="86695-139">Es folgt den gesamten Code in die *CostService.svc.cs* Datei:</span><span class="sxs-lookup"><span data-stu-id="86695-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

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

<span data-ttu-id="86695-140">Folgendes ist der vollständige Inhalt von der *WebForm1.aspx* Seite:</span><span class="sxs-lookup"><span data-stu-id="86695-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

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
