---
title: 'Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
ms.openlocfilehash: 3490b6fb89bfe6d7ac778078f58381bb5172e2fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288484"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="96e3c-102">Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="96e3c-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="96e3c-103">Ein häufiges Szenario in ASP.NET Web Forms-Anwendungen ist das Auffüllen einer Webseite mit Steuerelementen und das anschließende Durchführen einer bestimmten Aktion, auf deren Steuerelement der Benutzer klickt.</span><span class="sxs-lookup"><span data-stu-id="96e3c-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="96e3c-104">Beispielsweise löst ein <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType>-Steuerelement ein Ereignis aus, wenn der Benutzer auf der Webseite darauf klickt.</span><span class="sxs-lookup"><span data-stu-id="96e3c-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="96e3c-105">Durch die Verarbeitung des Ereignisses kann Ihre Anwendung die zugehörige Anwendungslogik für diesen Schaltflächenklick ausführen.</span><span class="sxs-lookup"><span data-stu-id="96e3c-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="96e3c-106">So behandeln Sie ein Click-Ereignis auf einer Webseite</span><span class="sxs-lookup"><span data-stu-id="96e3c-106">To handle a button click event on a webpage</span></span>  
  
1. <span data-ttu-id="96e3c-107">Erstellen Sie eine ASP.NET Web Forms-Seite (Webseite), bei der der `OnClick`-Wert des <xref:System.Web.UI.WebControls.Button>-Steuerelements auf den Namen der Methode festgelegt ist, die Sie im nächsten Schritt definieren.</span><span class="sxs-lookup"><span data-stu-id="96e3c-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. <span data-ttu-id="96e3c-108">Definieren Sie einen Ereignishandler, der der Delegatsignatur des <xref:System.Web.UI.WebControls.Button.Click>-Ereignisses entspricht und den von Ihnen für den `OnClick`-Wert definierten Namen trägt.</span><span class="sxs-lookup"><span data-stu-id="96e3c-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <span data-ttu-id="96e3c-109">Das <xref:System.Web.UI.WebControls.Button.Click>-Ereignis verwendet die <xref:System.EventHandler>-Klasse für den Delegattyp und die <xref:System.EventArgs>-Klasse für die Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="96e3c-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="96e3c-110">Das Framework für ASP.NET-Seiten generiert automatisch Code, der eine <xref:System.EventHandler>-Instanz erstellt und diese Delegatinstanz dem <xref:System.Web.UI.WebControls.Button.Click>-Ereignis der <xref:System.Web.UI.WebControls.Button>-Instanz hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="96e3c-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3. <span data-ttu-id="96e3c-111">Fügen Sie in der in Schritt 2 definierten Ereignishandlermethode Code hinzu, um die beim Auftreten des Ereignisses erforderlichen Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96e3c-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e3c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96e3c-112">See also</span></span>

- [<span data-ttu-id="96e3c-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="96e3c-113">Events</span></span>](index.md)
