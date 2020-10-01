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
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift

In diesem Thema wird gezeigt, wie Sie mit Visual Studio einen AJAX-fähigen Windows Communication Foundation (WCF)-Dienst und einen ASP.NET-Client erstellen, der auf den Dienst zugreift.

## <a name="create-an-aspnet-web-app"></a>Erstellen einer ASP.NET-Web-App

1. Öffnen Sie Visual Studio.

1. Wählen Sie im Menü **Datei** die Option **Neues**  >  **Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neues Projekt** die **Installed**  >  Kategorie**Visual c#**  >  -**webkategorie** , und wählen Sie dann **ASP.NET-Webanwendung (.NET Framework)** aus.

1. Nennen Sie das **Projekt,** und klicken Sie auf **OK**.

1. Wählen Sie im Dialogfeld **neue ASP.NET Webanwendung** die Option **leer** aus, und klicken Sie dann auf **OK**.

   ![Dialogfeld "ASP.net Web App type" in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Webformular hinzufügen

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie **Add**  >  **Neues Element**hinzufügen aus.

1. Erweitern Sie im Dialogfeld **Neues Element hinzufügen** **die**  >  Kategorie**Visual c#**  >  -**webkategorie** , und wählen Sie dann die **Web Form** -Vorlage aus.

1. Akzeptieren Sie den Standardnamen (**WebForm1**), und wählen Sie dann **Hinzufügen**aus.

   *WebForm1. aspx* wird in der **Quell** Ansicht geöffnet.

1. Fügen Sie das folgende Markup innerhalb der **\<body>** Tags ein:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Erstellen eines AJAX-aktivierten WCF-Dienstanbieter

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt Sandwich Services, und wählen Sie **Add**  >  **Neues Element**hinzufügen aus.

1. Erweitern Sie im Dialogfeld **Neues Element hinzufügen** **die**  >  **Visual c#**  >  -**webkategorie** , und wählen Sie dann die Vorlage **WCF-Dienst (AJAX-aktiviert)** aus.

   ![Element Vorlage für den WCF-Dienst (Ajax-fähig) in Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Nennen Sie den Dienst " **CostService** ", und wählen Sie dann **Hinzufügen**

   *CostService.svc.cs* wird im Editor geöffnet.

1. Implementieren Sie den-Vorgang im-Dienst. Fügen Sie der CostService-Klasse die folgende Methode hinzu, um die Kosten einer Menge von Sandwiches zu berechnen:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Konfigurieren des Clients für den Zugriff auf den Dienst

1. Öffnen Sie die Datei *WebForm1. aspx* , und wählen Sie die **Entwurfs** Ansicht aus.

2. Wählen Sie im Menü **Ansicht** die Option **Toolbox**aus.

3. Erweitern Sie den Knoten **AJAX-Erweiterungen** , und ziehen Sie **ScriptManager** per Drag & amp; Drop auf das Formular.

4. Fügen Sie in der **Quell** Ansicht den folgenden Code zwischen den- **\<ScriptManager>** Tags hinzu, um den Pfad zum WCF-Dienst anzugeben:

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. Fügen Sie den Code für die JavaScript-Funktion hinzu `Calculate()` . Platzieren Sie den folgenden Code im **Head** -Abschnitt des Webformulars:

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

   Dieser Code Ruft die-Methode von "CostService" auf, um den Preis für drei Sandwiches zu berechnen, und zeigt dann das Ergebnis in der Spanne mit dem Namen **additionresult**an.

## <a name="run-the-program"></a>Ausführen des Programms

Stellen Sie sicher, dass *WebForm1. aspx* den Fokus besitzt, und drücken Sie dann die Schaltfläche **Start** , um den WebClient zu starten. Die Schaltfläche hat ein grünes Dreieck und sagt etwas wie **IIS Express (Microsoft Edge)**. Alternativ können Sie <kbd>F5</kbd>drücken. Klicken Sie auf den **Preis der drei Sandwiches** -Schaltfläche, um die erwartete Ausgabe von "3,75" zu generieren.

## <a name="example"></a>Beispiel

Im folgenden finden Sie den vollständigen Code in der Datei *CostService.svc.cs* :

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

Im folgenden finden Sie den vollständigen Inhalt der Seite *WebForm1. aspx* :

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
