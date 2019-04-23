---
title: 'Vorgehensweise: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: cf1391e88c03095e0851d75ae6d50f8e809d13e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295613"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="91e9f-102">Vorgehensweise: Implementieren der bidirektionalen Kommunikation zwischen DHTML-Code und Clientanwendungscode</span><span class="sxs-lookup"><span data-stu-id="91e9f-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>
<span data-ttu-id="91e9f-103">Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement können Sie verwenden, um Ihren Windows Forms-Clientanwendungen vorhandenen DHTML-Webanwendungscode (dynamisches HTML) hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="91e9f-104">Dies ist hilfreich, wenn Sie viel Zeit in die Erstellung DHTML-basierter Steuerelemente investiert haben und von den Möglichkeiten der Windows Forms-Benutzeroberfläche profitieren möchten, ohne vorhandenen Code umschreiben zu müssen. </span><span class="sxs-lookup"><span data-stu-id="91e9f-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>  
  
 <span data-ttu-id="91e9f-105">Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement ermöglicht es Ihnen, mithilfe der <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>- und der <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft bidirektionale Kommunikation zwischen Ihrem Clientanwendungscode und Ihrem Webseitenskriptcode zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="91e9f-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="91e9f-106">Darüber hinaus können Sie das <xref:System.Windows.Forms.WebBrowser>-Steuerelement so konfigurieren, dass die Websteuerelemente sich nahtlos mit anderen Steuerelementen auf Ihrem Anwendungsformular einfügen, wodurch deren DHTML-Implementierung ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="91e9f-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="91e9f-107">Damit sich die Steuerelemente nahtlos einfügen, formatieren Sie die angezeigte Seite so, dass die Hintergrundfarbe und der visuelle Stil mit dem restlichen Formular übereinstimmen, und verwenden Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>-, die <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>- und die <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A>-Eigenschaft, um die Standardbrowserfeatures zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="91e9f-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="91e9f-108">So betten Sie DHTML in Ihre Windows Forms-Anwendung ein</span><span class="sxs-lookup"><span data-stu-id="91e9f-108">To embed DHTML in your Windows Forms application</span></span>  
  
1. <span data-ttu-id="91e9f-109">Legen Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>-Steuerelement Dateien öffnet, die auf ihm abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="91e9f-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2. <span data-ttu-id="91e9f-110">Legen Sie die <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>-Eigenschaft auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>-Steuerelement sein Kontextmenü anzeigt, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt.</span><span class="sxs-lookup"><span data-stu-id="91e9f-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3. <span data-ttu-id="91e9f-111">Legen Sie die <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A>-Eigenschaft des Steuerelements auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>-Steuerelement auf Tastenkombinationen reagiert.</span><span class="sxs-lookup"><span data-stu-id="91e9f-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4. <span data-ttu-id="91e9f-112">Legen Sie die <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>-Eigenschaft im Konstruktor des Formulars oder in einem <xref:System.Windows.Forms.Form.Load>-Ereignishandler fest.</span><span class="sxs-lookup"><span data-stu-id="91e9f-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or a <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
     <span data-ttu-id="91e9f-113">Im folgenden Code wird die Formularklasse selbst für das Skriptobjekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="91e9f-113">The following code uses the form class itself for the scripting object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91e9f-114">Das COM (Component Object Model) muss auf das Skriptobjekt zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="91e9f-114">Component Object Model (COM) must be able to access the scripting object.</span></span> <span data-ttu-id="91e9f-115">Um das Formular für COM sichtbar zu machen, fügen Sie Ihrer Formularklasse das <xref:System.Runtime.InteropServices.ComVisibleAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="91e9f-115">To make your form visible to COM, add the <xref:System.Runtime.InteropServices.ComVisibleAttribute> attribute to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5. <span data-ttu-id="91e9f-116">Implementieren Sie öffentliche Eigenschaften oder Methoden in Ihrem Anwendungscode, den Ihr Skriptcode verwendet.</span><span class="sxs-lookup"><span data-stu-id="91e9f-116">Implement public properties or methods in your application code that your script code will use.</span></span>  
  
     <span data-ttu-id="91e9f-117">Wenn Sie beispielsweise die Formularklasse für das Skriptobjekt verwenden, fügen Sie der Formularklasse folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="91e9f-117">For example, if you use the form class for the scripting object, add the following code to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6. <span data-ttu-id="91e9f-118">Verwenden Sie das `window.external`-Objekt in Ihrem Skriptcode, um auf öffentliche Eigenschaften und Methoden des angegebenen Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-118">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>  
  
     <span data-ttu-id="91e9f-119">Der folgende HTML-Code veranschaulicht, wie eine Methode des Skriptobjekts über Klicken auf eine Schaltfläche aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="91e9f-119">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="91e9f-120">Kopieren Sie diesen Code in das BODY-Element eines HTML-Dokuments, das Sie mithilfe der <xref:System.Windows.Forms.WebBrowser.Navigate%2A>-Methode des Steuerelements laden oder das Sie der <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft des Steuerelements zuweisen .</span><span class="sxs-lookup"><span data-stu-id="91e9f-120">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7. <span data-ttu-id="91e9f-121">Implementieren Sie Funktionen in Ihrem Skriptcode, den Ihr Anwendungscode verwendet.</span><span class="sxs-lookup"><span data-stu-id="91e9f-121">Implement functions in your script code that your application code will use.</span></span>  
  
     <span data-ttu-id="91e9f-122">Das folgende HTML-SCRIPT-Element stellt eine Beispielfunktion bereit.</span><span class="sxs-lookup"><span data-stu-id="91e9f-122">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="91e9f-123">Kopieren Sie diesen Code in das HEAD-Element eines HTML-Dokuments, das Sie mithilfe der <xref:System.Windows.Forms.WebBrowser.Navigate%2A>-Methode des Steuerelements laden oder das Sie der <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft des Steuerelements zuweisen .</span><span class="sxs-lookup"><span data-stu-id="91e9f-123">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8. <span data-ttu-id="91e9f-124">Verwenden Sie die <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft, um aus Ihrem Clientanwendungscode auf den Skriptcode zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-124">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>  
  
     <span data-ttu-id="91e9f-125">Fügen Sie beispielsweise den folgenden Code dem <xref:System.Windows.Forms.Control.Click>-Ereignishandler einer Schaltfläche hinzu.</span><span class="sxs-lookup"><span data-stu-id="91e9f-125">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. <span data-ttu-id="91e9f-126">Nachdem Sie das Debuggen des DHTML-Codes abgeschlossen haben, legen Sie die <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A>-Eigenschaft des Steuerelements auf `true` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser>-Steuerelement Fehlermeldungen für Skriptcodeprobleme angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91e9f-126">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="91e9f-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91e9f-127">Example</span></span>  
 <span data-ttu-id="91e9f-128">Mit dem folgenden Codebeispiel steht Ihnen eine vollständige Beispielanwendung zur Verfügung, die Ihnen dabei hilft, sich mit dieser Funktion vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-128">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="91e9f-129">Der HTML-Code wird nicht aus einer separaten HTML-Datei, sondern über die <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft in das <xref:System.Windows.Forms.WebBrowser>-Steuerelement geladen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-129">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91e9f-130">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="91e9f-130">Compiling the Code</span></span>  
 <span data-ttu-id="91e9f-131">Dieser Code erfordert:</span><span class="sxs-lookup"><span data-stu-id="91e9f-131">This code requires:</span></span>  
  
-   <span data-ttu-id="91e9f-132">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="91e9f-132">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="91e9f-133">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="91e9f-133">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="91e9f-134">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="91e9f-134">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e9f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91e9f-135">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [<span data-ttu-id="91e9f-136">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="91e9f-136">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
