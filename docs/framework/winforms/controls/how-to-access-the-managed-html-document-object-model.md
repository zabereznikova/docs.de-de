---
title: 'Vorgehensweise: Zugriff auf das verwaltete HTML-Dokumentobjektmodell'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 8799ac9897771a7cdf5a1e473914f461e435c061
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637150"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="fdafe-102">Vorgehensweise: Zugriff auf das verwaltete HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="fdafe-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="fdafe-103">Sie können auf das verwaltete HTML-Dokumentobjektmodell (DOM) von zwei Anwendungsarten aus zugreifen:</span><span class="sxs-lookup"><span data-stu-id="fdafe-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
-   <span data-ttu-id="fdafe-104">Eine Windows Forms-Anwendung (EXE), die das verwaltete <xref:System.Windows.Forms.WebBrowser>-Steuerelement gehostet hat.</span><span class="sxs-lookup"><span data-stu-id="fdafe-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="fdafe-105">Diese beiden Technologien ergänzen sich gegenseitig, wobei das <xref:System.Windows.Forms.WebBrowser>-Steuerelement dem Benutzer die Seite anzeigt und das HTML-DOM die logische Struktur des Dokuments darstellt.</span><span class="sxs-lookup"><span data-stu-id="fdafe-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
-   <span data-ttu-id="fdafe-106">Ein Windows Forms-<xref:System.Windows.Forms.UserControl>, das innerhalb von Internet Explorer gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fdafe-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="fdafe-107">Sie können auf das HTML-DOM zugreifen, das die Seite darstellt, auf der das <xref:System.Windows.Forms.UserControl> gehostet wird, um beispielsweise unter anderem die Dokumentstruktur zu ändern oder modale Dialogfelder zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fdafe-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="fdafe-108">So greifen Sie über eine Windows Forms-Anwendung auf das DOM zu</span><span class="sxs-lookup"><span data-stu-id="fdafe-108">To access DOM from a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="fdafe-109">Hosten Sie ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement innerhalb der Windows Forms-Anwendung, und überwachen Sie es auf das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fdafe-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="fdafe-110">Ausführliche Informationen über das Hosten von Steuerelementen und das Überwachen auf Ereignisse finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="fdafe-110">For details on hosting controls and monitoring for events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
2.  <span data-ttu-id="fdafe-111">Rufen Sie das <xref:System.Windows.Forms.HtmlDocument> für die aktuelle Seite ab, indem Sie auf die <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdafe-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="fdafe-112">So greifen Sie von einem in Internet Explorer gehosteten UserControl auf das DOM zu</span><span class="sxs-lookup"><span data-stu-id="fdafe-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="fdafe-113">Erstellen Sie Ihre eigene benutzerdefinierte abgeleitete Klasse der <xref:System.Windows.Forms.UserControl>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdafe-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="fdafe-114">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).</span><span class="sxs-lookup"><span data-stu-id="fdafe-114">For more information, see [How to: Author Composite Controls](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).</span></span>  
  
2.  <span data-ttu-id="fdafe-115">Platzieren Sie den folgenden Code innerhalb des Load-Ereignishandlers für das <xref:System.Windows.Forms.UserControl>:</span><span class="sxs-lookup"><span data-stu-id="fdafe-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fdafe-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="fdafe-116">Robust Programming</span></span>  
  
1.  <span data-ttu-id="fdafe-117">Wenn Sie das DOM mithilfe des <xref:System.Windows.Forms.WebBrowser>-Steuerelements verwenden, sollten Sie stets so lange warten, bis das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis auftritt, bevor Sie versuchen, auf die <xref:System.Windows.Forms.WebBrowser.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.WebBrowser>-Steuerelements zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdafe-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="fdafe-118">Das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>-Ereignis wird ausgelöst, nachdem das gesamte Dokument geladen wurde. Wenn Sie das DOM vorher verwenden, besteht das Risiko, eine Laufzeitausnahme in der Anwendung zu verursachen.</span><span class="sxs-lookup"><span data-stu-id="fdafe-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fdafe-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fdafe-119">.NET Framework Security</span></span>  
  
1.  <span data-ttu-id="fdafe-120">Die Anwendung oder das <xref:System.Windows.Forms.UserControl> setzen volle Vertrauenswürdigkeit voraus, um auf das verwaltete HTML-DOM zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdafe-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="fdafe-121">Wenn Sie eine Windows Forms-Anwendung mit [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] bereitstellen, können Sie volle Vertrauenswürdigkeit entweder über erweiterte Berechtigungen oder die Bereitstellung vertrauenswürdiger Anwendungen anfordern; ausführliche Informationen finden Sie unter [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications).</span><span class="sxs-lookup"><span data-stu-id="fdafe-121">If you are deploying a Windows Forms application using [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdafe-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdafe-122">See also</span></span>
- [<span data-ttu-id="fdafe-123">Verwenden des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="fdafe-123">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
