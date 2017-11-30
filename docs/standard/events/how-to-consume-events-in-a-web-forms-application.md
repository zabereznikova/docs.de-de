---
title: 'Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bdb0a6be309f27348ba13bf93fd5aedd3c66a792
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="46f93-102">Gewusst wie: Verarbeiten von Ereignissen in einer Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="46f93-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="46f93-103">Ein häufiges Szenario in ASP.NET Web Forms-Anwendungen werden von einer Webseite mit Steuerelementen füllen, und führen Sie dann eine bestimmte Aktion, die steuern, dass der Benutzer klickt auf Grundlage ab.</span><span class="sxs-lookup"><span data-stu-id="46f93-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="46f93-104">Angenommen, ein <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> Steuerelement löst ein Ereignis aus, wenn der Benutzer er auf der Webseite klickt.</span><span class="sxs-lookup"><span data-stu-id="46f93-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="46f93-105">Die Anwendung kann die zugehörige Anwendungslogik klicken auf die Schaltfläche ausführen, indem Sie die Behandlung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="46f93-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="46f93-106">So behandeln Sie ein Click-Ereignis auf einer Webseite</span><span class="sxs-lookup"><span data-stu-id="46f93-106">To handle a button click event on a webpage</span></span>  
  
1.  <span data-ttu-id="46f93-107">Erstellen eine ASP.NET Web Forms-Seite (Webseite), wurde eine <xref:System.Web.UI.WebControls.Button> steuern, mit der `OnClick` Wert festgelegt wird, um den Namen der Methode, die Sie im nächsten Schritt definieren.</span><span class="sxs-lookup"><span data-stu-id="46f93-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  <span data-ttu-id="46f93-108">Definieren Sie einen Ereignishandler, entspricht die <xref:System.Web.UI.WebControls.Button.Click> Ereignis Delegatsignatur und, trägt den Namen, die Sie definiert, für die `OnClick` Wert.</span><span class="sxs-lookup"><span data-stu-id="46f93-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
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
  
     <span data-ttu-id="46f93-109">Die <xref:System.Web.UI.WebControls.Button.Click> Ereignis verwendet die <xref:System.EventHandler> Klasse für den Delegattyp und die <xref:System.EventArgs> Klasse für die Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="46f93-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="46f93-110">Das ASP.NET-Seitenframework generiert automatisch Code, der eine Instanz erstellt <xref:System.EventHandler> und fügt diese Delegatinstanz mit der <xref:System.Web.UI.WebControls.Button.Click> -Ereignis für die <xref:System.Web.UI.WebControls.Button> Instanz.</span><span class="sxs-lookup"><span data-stu-id="46f93-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3.  <span data-ttu-id="46f93-111">Fügen Sie im Ereignistext Ereignishandlermethode, die Sie in Schritt 2, definiert Code erforderliche Aktionen auszuführen, die erforderlich sind, wenn das Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="46f93-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f93-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46f93-112">See Also</span></span>  
 [<span data-ttu-id="46f93-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="46f93-113">Events</span></span>](../../../docs/standard/events/index.md)
