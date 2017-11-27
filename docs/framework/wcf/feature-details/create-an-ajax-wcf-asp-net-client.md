---
title: 'Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45a186b0d281976f3d6ad554d75742ba0f1cd50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="9cf18-102">Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift</span><span class="sxs-lookup"><span data-stu-id="9cf18-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="9cf18-103">In diesem Thema wird gezeigt, wie Sie mit Visual&#160;Studio&#160;2008 einen AJAX-aktivierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst und einen ASP.NET-Client, der auf den Dienst zugreift, erstellen.</span><span class="sxs-lookup"><span data-stu-id="9cf18-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="9cf18-104">Der Code für den Dienst und für den Client wird im Abschnitt mit dem Beispiel nach den Schritten bereitgestellt, in denen die Erstellung des Diensts und des Clients beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="9cf18-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="9cf18-105">So erstellen Sie die ASP.NET-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="9cf18-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="9cf18-106">Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cf18-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="9cf18-107">Aus der **Datei** klicken Sie im Menü **neu**, klicken Sie dann **Projekt**, klicken Sie dann **Web**, und wählen Sie dann **ASP.NET-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="9cf18-108">Nennen Sie das Projekt `SandwichServices` , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="9cf18-109">So erstellen Sie den AJAX-aktivierten WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="9cf18-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="9cf18-110">Mit der rechten Maustaste die `SandwichServices` -Projekt in der **Projektmappen-Explorer** und wählen Sie **hinzufügen**, klicken Sie dann **neues Element**, und klicken Sie dann **AJAX-aktivierter WCF-Dienst** .</span><span class="sxs-lookup"><span data-stu-id="9cf18-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="9cf18-111">Benennen Sie den Dienst `CostService` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="9cf18-112">Öffnen Sie die Datei CostService.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="9cf18-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="9cf18-113">Geben Sie die `Namespace` für <xref:System.ServiceModel.ServiceContractAttribute> als `SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="9cf18-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  <span data-ttu-id="9cf18-114">Implementieren Sie die Vorgänge im Dienst.</span><span class="sxs-lookup"><span data-stu-id="9cf18-114">Implement the operations in the service.</span></span> <span data-ttu-id="9cf18-115">Fügen Sie allen Vorgängen das <xref:System.ServiceModel.OperationContractAttribute> hinzu, um anzugeben, dass sie ein Teil des Vertrags sind.</span><span class="sxs-lookup"><span data-stu-id="9cf18-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="9cf18-116">Im folgenden Beispiel wird eine Methode implementiert, die die Kosten für eine bestimmte Menge Sandwiches zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9cf18-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="9cf18-117">So konfigurieren Sie den Client für den Zugriff auf den Dienst</span><span class="sxs-lookup"><span data-stu-id="9cf18-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="9cf18-118">Öffnen Sie die Seite "default.aspx", und wählen Sie die **Entwurf** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9cf18-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="9cf18-119">Aus der **Ansicht** klicken Sie im Menü **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="9cf18-120">Erweitern Sie die **AJAX-Erweiterungen** Knoten und Drag & Drop eine **ScriptManager** auf die Seite Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9cf18-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="9cf18-121">Mit der rechten Maustaste die **ScriptManager** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="9cf18-122">Erweitern Sie die **Services** Sammlung in der **Eigenschaften** Fenster zu öffnen die **ServiceReference-Auflistungs-Editor** Fenster.</span><span class="sxs-lookup"><span data-stu-id="9cf18-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="9cf18-123">Klicken Sie auf **hinzufügen**, geben Sie `CostService.svc` als die **Pfad** auf die verwiesen wird, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="9cf18-124">Erweitern Sie die **HTML** Knoten in der **Toolbox** und ziehen Sie ein **Eingabe (Schaltfläche)** auf die Seite Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9cf18-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="9cf18-125">Mit der rechten Maustaste die **Schaltfläche** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9cf18-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="9cf18-126">Ändern der **Wert** Feld `Price for 3 Sandwiches`.</span><span class="sxs-lookup"><span data-stu-id="9cf18-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="9cf18-127">Doppelklicken Sie auf die **Schaltfläche** zum Zugriff auf die JavaScript-Code.</span><span class="sxs-lookup"><span data-stu-id="9cf18-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="9cf18-128">Übergeben Sie den folgenden JavaScript-Code in der <`script`> Element.</span><span class="sxs-lookup"><span data-stu-id="9cf18-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="9cf18-129">So greifen Sie über den Client auf den Dienst zu</span><span class="sxs-lookup"><span data-stu-id="9cf18-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="9cf18-130">Verwenden Sie STRG&#160;+&#160;F5, um den Dienst und den Webclient zu starten.</span><span class="sxs-lookup"><span data-stu-id="9cf18-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="9cf18-131">Klicken Sie auf die **Price for 3 Grilled Sandwiches** Schaltfläche, um die erwartete Ausgabe "3,75" zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9cf18-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cf18-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cf18-132">Example</span></span>  
 <span data-ttu-id="9cf18-133">Dieses Beispiel enthält den Dienstcode der Datei WCFService.svc.cs und den Clientcode der Datei Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9cf18-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     
