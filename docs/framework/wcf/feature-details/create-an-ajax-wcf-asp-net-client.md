---
title: Erstellen Sie in Visual Studio ein AJAX-aktivierten WCF-Dienst und einem ASP.NET-Client
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586129"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Vorgehensweise: Erstellen eines AJAX-aktivierten WCF-Diensts und eines ASP.NET-Clients, der auf den Dienst zugreift

In diesem Thema wird gezeigt, wie mit Visual Studio zum Erstellen einer AJAX-fähigen Windows Communication Foundation (WCF)-Dienst und einem ASP.NET-Client, die auf den Dienst zugreift.

## <a name="create-an-aspnet-web-app"></a>Erstellen einer ASP.NET-Web-App

1. Öffnen Sie Visual Studio.

1. Von der **Datei** , wählen Sie im Menü **neu** > **Projekt**

1. In der **neues Projekt** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie **ASP.NET-Webanwendung ((.NET Framework)**.

1. Nennen Sie das Projekt **SandwichServices** , und klicken Sie auf **OK**.

1. In der **neue ASP.NET-Webanwendung** wählen Sie im Dialogfeld **leere** und wählen Sie dann **OK**.

   ![Dialogfeld für ASP.NET Web-app-Typ in Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Ein Web Form hinzufügen

1. Mit der rechten Maustaste in des Projekts SandwichServices im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Element**.

1. In der **neues Element hinzufügen** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie die **Webformular** Vorlage.

1. Übernehmen Sie den Standardnamen (**WebForm1**), und wählen Sie dann **hinzufügen**.

   *WebForm1.aspx* öffnet im **Quelle** anzeigen.

1. Fügen Sie das folgende Markup innerhalb der  **\<Text >** Tags:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Erstellen eines AJAX-aktivierten WCF-Diensts

1. Mit der rechten Maustaste in des Projekts SandwichServices im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Element**.

1. In der **neues Element hinzufügen** Dialogfeld erweitern Sie die **installiert** > **Visual C#-** > **Web** (Kategorie), und klicken Sie dann Wählen Sie die **WCF-Dienst (AJAX-fähig)** Vorlage.

   ![WCF-Dienst (AJAX-fähig) Elementvorlage in Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Nennen Sie den Dienst **CostService** und wählen Sie dann **hinzufügen**.

   *CostService.svc.cs* im Editor geöffnet.

1. Implementieren Sie den Vorgang im Dienst. Fügen Sie auf die Berechnung der Kosten für eine Menge Sandwiches CostService Klasse die folgende Methode hinzu:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Konfigurieren des Clients für den Zugriff auf den Dienst

1. Öffnen der *WebForm1.aspx* und wählen Sie die **Entwurf** anzeigen.

2. Von der **Ansicht** , wählen Sie im Menü **Toolbox**.

3. Erweitern Sie die **AJAX-Erweiterungen** Knoten und Drag & Drop eine **ScriptManager** auf das Formular.

4. In der **Quelle** anzuzeigen, fügen Sie den folgenden Code zwischen den  **\<ScriptManager >** Tags aus, um den Pfad zum WCF-Dienst angeben:

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. Fügen Sie den Code für die Javascript-Funktion `Calculate()`. Platzieren Sie den folgenden Code in die **Head** Abschnitt des Webformulars:

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

   Dieser Code Ruft die Methode der CostService zum Berechnen des Preis für drei Sandwiches und zeigt dann das Ergebnis in der Spanne namens **AdditionResult**.

## <a name="run-the-program"></a>Ausführen des Programms

Stellen Sie sicher, dass *WebForm1.aspx* den Fokus besitzt, und drücken Sie dann die **starten** Schaltfläche, um den WebClient zu starten. Die Schaltfläche wurde ein grünes Dreieck und etwa sagt **IIS Express (Microsoft Edge)**. Sie können durch Drücken **F5**. Klicken Sie auf die **Preis 3 Sandwiches** Schaltfläche, um die erwartete Ausgabe "3,75" zu generieren.

## <a name="example-code"></a>Beispielcode

Es folgt den gesamten Code in die *CostService.svc.cs* Datei:

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

Folgendes ist der vollständige Inhalt von der *WebForm1.aspx* Seite:

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
