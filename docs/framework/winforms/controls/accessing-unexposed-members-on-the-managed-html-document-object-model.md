---
title: Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: d2fbccfb3ecd7716420ca951e86f728798d25258
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526432"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="9057a-102">Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="9057a-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="9057a-103">Das verwaltete HTML (DOKUMENTOBJEKTMODELL) enthält eine Klasse mit dem Namen <xref:System.Windows.Forms.HtmlElement> , verfügbar macht, die Eigenschaften, Methoden und Ereignisse, die alle HTML-Elemente gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="9057a-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="9057a-104">In einigen Fällen müssen Sie jedoch auf Member zuzugreifen, die nicht direkt von die verwaltete Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="9057a-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="9057a-105">In diesem Thema werden zwei Methoden für den Zugriff auf nicht verfügbar gemachte Member an, einschließlich untersucht [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] und VBScript-Funktionen, die innerhalb einer Webseite definiert.</span><span class="sxs-lookup"><span data-stu-id="9057a-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="9057a-106">Zugreifen auf nicht verfügbar gemachte Member über verwaltete Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9057a-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="9057a-107"><xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> vier Methoden bereit, die Zugriff auf nicht verfügbar gemachte Member ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9057a-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="9057a-108">Die folgende Tabelle zeigt die Typen und die entsprechenden Methoden.</span><span class="sxs-lookup"><span data-stu-id="9057a-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="9057a-109">Memberart</span><span class="sxs-lookup"><span data-stu-id="9057a-109">Member Type</span></span>|<span data-ttu-id="9057a-110">Methode(n)</span><span class="sxs-lookup"><span data-stu-id="9057a-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9057a-111">Eigenschaften (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="9057a-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="9057a-112">Methoden</span><span class="sxs-lookup"><span data-stu-id="9057a-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="9057a-113">Ereignisse (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="9057a-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="9057a-114">Ereignisse (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="9057a-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="9057a-115">Ereignisse (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="9057a-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="9057a-116">Wenn Sie diese Methoden verwenden, wird davon ausgegangen, dass Sie ein Element mit dem richtigen zugrunde liegenden Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9057a-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="9057a-117">Nehmen wir an, dass Sie überwachen möchten die `Submit` -Ereignis ein `FORM` Element auf einer HTML-Seite, sodass für einige erforderliche Verarbeitung ausgeführt werden können die `FORM`Werte, bevor die Benutzer an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="9057a-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="9057a-118">Im Idealfall, wenn Sie die Kontrolle über den HTML-Code haben, definieren Sie die `FORM` ein eindeutiges `ID` Attribut.</span><span class="sxs-lookup"><span data-stu-id="9057a-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="9057a-119">Nach dem Laden dieser Seite in der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, können Sie die <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> Methode zum Abrufen der `FORM` zur Laufzeit mit `form1` als Argument.</span><span class="sxs-lookup"><span data-stu-id="9057a-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="9057a-120">Zugreifen auf nicht verwalteten Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9057a-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="9057a-121">Sie können auch nicht verfügbar gemachte Member auf das verwaltete HTML-DOM zugreifen, mithilfe der nicht verwalteten Component Object Model (COM)-Schnittstellen, die von jeder DOM-Klasse verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="9057a-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="9057a-122">Dies wird empfohlen, wenn mehrere Aufrufe für nicht verfügbar gemachte Member vorgenommen werden muss oder nicht verfügbar gemachte Member andere nicht verwaltete Schnittstellen, die nicht vom verwalteten HTML DOM. umschlossen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="9057a-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="9057a-123">Die folgende Tabelle zeigt alle nicht verwalteten Schnittstellen, die über das verwaltete HTML-DOM. verfügbar gemacht werden</span><span class="sxs-lookup"><span data-stu-id="9057a-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="9057a-124">Klicken Sie auf jeden Link eine Erläuterung zur Verwendung sowie z. B. Code.</span><span class="sxs-lookup"><span data-stu-id="9057a-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="9057a-125">Typ</span><span class="sxs-lookup"><span data-stu-id="9057a-125">Type</span></span>|<span data-ttu-id="9057a-126">Nicht verwaltete Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9057a-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="9057a-127">Die einfachste Möglichkeit zum Verwenden von COM-Schnittstellen ist einen Verweis auf die nicht verwaltete Bibliothek von HTML-DOM (MSHTML.dll) von Ihrer Anwendung hinzufügen, obwohl dies nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9057a-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="9057a-128">Weitere Informationen finden Sie unter [Knowledge Base-Artikel 934368](http://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="9057a-128">For more information, see [Knowledge Base Article 934368](http://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="9057a-129">Zugreifen auf Skriptfunktionen</span><span class="sxs-lookup"><span data-stu-id="9057a-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="9057a-130">Eine HTML-Seite kann eine oder mehrere Funktionen definieren, indem Sie z. B. mithilfe einer Skriptsprache [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] oder VBScript.</span><span class="sxs-lookup"><span data-stu-id="9057a-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="9057a-131">Diese Funktionen befinden sich innerhalb von einer `SCRIPT` auf der Seite der Seite ", und kann bei Bedarf oder als Reaktion auf ein Ereignis ausgeführt werden, auf das DOM validiert werden.</span><span class="sxs-lookup"><span data-stu-id="9057a-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="9057a-132">Sie können alle Skriptfunktionen, die Sie definieren in einer HTML-Seite mit Aufrufen der <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9057a-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="9057a-133">Wenn Skriptmethode ein HTML-Element zurückgibt, können Sie eine Umwandlung verwenden, um dieses Ergebnis zu konvertieren einer <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="9057a-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="9057a-134">Ausführliche Informationen und Beispielcode finden Sie unter <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span><span class="sxs-lookup"><span data-stu-id="9057a-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9057a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9057a-135">See Also</span></span>  
 [<span data-ttu-id="9057a-136">Verwenden des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="9057a-136">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
