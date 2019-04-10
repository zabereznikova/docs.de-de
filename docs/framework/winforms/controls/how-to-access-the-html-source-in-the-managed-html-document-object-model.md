---
title: 'Vorgehensweise: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: f2306e3405aa0ff37060d987bdc82b58fbaa7784
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345559"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="3c43b-102">Vorgehensweise: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="3c43b-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="3c43b-103">Die <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A>-Eigenschaft und die <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements geben den HTML-Code des aktuellen Dokuments zurück, der bei der ersten Anzeige verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3c43b-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="3c43b-104">Wenn Sie jedoch die Seite mithilfe von Methoden- und Eigenschaftenaufrufen wie <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> und <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A> ändern, werden diese Änderungen nicht angezeigt, wenn Sie <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> und <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3c43b-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="3c43b-105">Um die aktuelle HTML-Quelle für das DOM zu erhalten, müssen Sie die <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A>-Eigenschaft des HTML-Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3c43b-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="3c43b-106">Im folgenden Verfahren wird gezeigt, wie die dynamische Quelle abgerufen und in einem separaten Kontextmenü angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3c43b-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="3c43b-107">Abrufen der dynamischen Quelle mit der OuterHtml-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3c43b-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1. <span data-ttu-id="3c43b-108">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3c43b-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="3c43b-109">Beginnen Sie mit einem einzelnen <xref:System.Windows.Forms.Form>, und nennen Sie sie `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3c43b-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2. <span data-ttu-id="3c43b-110">Host der <xref:System.Windows.Forms.WebBrowser> -Steuerelement in der Windows Forms-Anwendung, und nennen Sie sie `WebBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="3c43b-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="3c43b-111">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="3c43b-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3. <span data-ttu-id="3c43b-112">Erstellen Sie eine zweite <xref:System.Windows.Forms.Form> in Ihrer Anwendung namens `CodeForm`.</span><span class="sxs-lookup"><span data-stu-id="3c43b-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4. <span data-ttu-id="3c43b-113">Hinzufügen einer <xref:System.Windows.Forms.RichTextBox> die Steuerung an `CodeForm` und legen Sie dessen <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft `Fill`.</span><span class="sxs-lookup"><span data-stu-id="3c43b-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5. <span data-ttu-id="3c43b-114">Erstellen Sie eine öffentliche Eigenschaft auf `CodeForm` namens `Code`.</span><span class="sxs-lookup"><span data-stu-id="3c43b-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6. <span data-ttu-id="3c43b-115">Hinzufügen einer <xref:System.Windows.Forms.Button> Steuerelement mit dem Namen `Button1` auf Ihre <xref:System.Windows.Forms.Form>, und überwachen Sie auf die <xref:System.Windows.Forms.Control.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3c43b-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="3c43b-116">Weitere Informationen zum Überwachen von Ereignissen finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c43b-116">For details on monitoring events, see [Events](../../../standard/events/index.md).</span></span>  
  
7. <span data-ttu-id="3c43b-117">Fügen Sie dem <xref:System.Windows.Forms.Control.Click>-Ereignishandler den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c43b-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3c43b-118">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="3c43b-118">Robust Programming</span></span>  
 <span data-ttu-id="3c43b-119">Testen Sie immer zuerst den Wert von <xref:System.Windows.Forms.WebBrowser.Document%2A>, bevor Sie einen Abruf versuchen.</span><span class="sxs-lookup"><span data-stu-id="3c43b-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="3c43b-120">Wenn die aktuelle Seite noch nicht vollständig geladen wurde, kann <xref:System.Windows.Forms.WebBrowser.Document%2A> oder ein bzw. mehrere untergeordnete Objekte möglicherweise nicht initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c43b-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c43b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c43b-121">See also</span></span>

- [<span data-ttu-id="3c43b-122">Verwenden des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="3c43b-122">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
- [<span data-ttu-id="3c43b-123">Übersicht über das WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3c43b-123">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
