---
title: "Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift
In diesem Thema wird gezeigt, wie Sie mit Visual&#160;Studio&#160;2008 einen AJAX-aktivierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst und einen ASP.NET-Client, der auf den Dienst zugreift, erstellen. Der Code für den Dienst und für den Client wird im Abschnitt mit dem Beispiel nach den Schritten bereitgestellt, in denen die Erstellung des Diensts und des Clients beschrieben ist.  
  
### <a name="to-create-the-aspnet-client-application"></a>So erstellen Sie die ASP.NET-Clientanwendung  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Aus der **Datei** klicken Sie im Menü **neu**, dann **Projekt**, dann **Web**, und wählen Sie dann **ASP.NET-Webanwendung**.  
  
3.  Nennen Sie das Projekt `SandwichServices` , und klicken Sie auf **OK**.  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a>So erstellen Sie den AJAX-aktivierten WCF-Dienst  
  
1.  Mit der rechten Maustaste die `SandwichServices` Projekt die **Projektmappen-Explorer** und wählen Sie **hinzufügen**, dann **neues Element**, und klicken Sie dann **AJAX-aktivierter WCF-Dienst**.  
  
2.  Benennen Sie den Dienst `CostService` in der **Namen** ein, und klicken Sie auf **hinzufügen**.  
  
3.  Öffnen Sie die Datei CostService.svc.cs.  
  
4.  Geben Sie die `Namespace` für <xref:System.ServiceModel.ServiceContractAttribute> als `SandwichService`:  
  
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
  
5.  Implementieren Sie die Vorgänge im Dienst. Hinzufügen der <xref:System.ServiceModel.OperationContractAttribute> für die einzelnen Vorgänge um anzugeben, dass sie Teil des Vertrags sind. Im folgenden Beispiel wird eine Methode implementiert, die die Kosten für eine bestimmte Menge Sandwiches zurückgibt.  
  
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
  
### <a name="to-configure-the-client-to-access-the-service"></a>So konfigurieren Sie den Client für den Zugriff auf den Dienst  
  
1.  Öffnen Sie die Seite Default.aspx, und wählen Sie die **Design** anzeigen.  
  
2.  Aus der **Ansicht** klicken Sie im Menü **Toolbox**.  
  
3.  Erweitern Sie die **AJAX Extensions** Knoten und Drag & Drop eine **ScriptManager** auf die Seite Default.aspx.  
  
4.  Mit der rechten Maustaste die **ScriptManager** , und wählen Sie **Eigenschaften**.  
  
5.  Erweitern Sie die **Services** -Auflistung in die **Eigenschaften** Fenster zu öffnen der **ServiceReference-Auflistungs-Editor** Fenster.  
  
6.  Klicken Sie auf **hinzufügen**, geben Sie `CostService.svc` als die **Pfad** verwiesen wird, und klicken Sie auf **OK**.  
  
7.  Erweitern Sie die **HTML** Knoten in der **Toolbox** und ziehen Sie ein **Eingabe (Schaltfläche)** auf die Seite Default.aspx.  
  
8.  Mit der rechten Maustaste die **Schaltfläche** , und wählen Sie **Eigenschaften**.  
  
9. Ändern der **Wert** Feld `Price for 3 Sandwiches`.  
  
10. Doppelklicken Sie auf die **Schaltfläche** Zugriff auf die JavaScript-Code.  
  
11. Übergeben Sie den folgenden JavaScript-Code innerhalb der `script`> Element.  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a>So greifen Sie über den Client auf den Dienst zu  
  
1.  Verwenden Sie STRG&#160;+&#160;F5, um den Dienst und den Webclient zu starten. Klicken Sie auf die **Price for 3 Grilled Sandwiches** Schaltfläche, um die erwartete Ausgabe "3,75" zu generieren.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält den Dienstcode der Datei WCFService.svc.cs und den Clientcode der Datei Default.aspx.  
  
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
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->