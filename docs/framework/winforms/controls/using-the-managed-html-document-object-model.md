---
title: Verwenden des verwalteten HTML-Dokumentobjektmodells
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 7800311895d1c0fac43577076226a68712164f60
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625062"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="8b9e0-102">Verwenden des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="8b9e0-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="8b9e0-103">Das verwaltete HTML Document Object Model (DOM) stellt einen Wrapper, der auf der Grundlage der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] für die HTML-Klassen, die von Internet Explorer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="8b9e0-104">Verwenden Sie diese Klassen zum Bearbeiten von HTML-Seiten gehostet werden, der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, oder um neue Seiten vom Anfang zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b9e0-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8b9e0-105">In This Section</span></span>  
 [<span data-ttu-id="8b9e0-106">Gewusst wie: Zugreifen auf das verwaltete HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="8b9e0-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8b9e0-107">Beschreibt, wie Sie eine gültige Instanz des erhalten <xref:System.Windows.Forms.HtmlDocument> aus einer Windows Forms-Anwendung oder ein <xref:System.Windows.Forms.UserControl> in Internet Explorer gehostet.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="8b9e0-108">Gewusst wie: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="8b9e0-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8b9e0-109">Beschreibt, wie Sie die ursprüngliche, nicht modifiziertes HTML-Quelle zu erhalten, und wie Sie die "live"-Quelle zu erhalten, die den aktuellen Zustand des DOM widerspiegelt</span><span class="sxs-lookup"><span data-stu-id="8b9e0-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="8b9e0-110">Gewusst wie: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="8b9e0-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8b9e0-111">Beschreibt die Formate bearbeiten, die zur Steuerung der visuellen Darstellung von Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="8b9e0-112">Zugreifen auf Frames im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="8b9e0-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8b9e0-113">Beschreibt, welche Frames und Framesets sind und wie Sie den Zugriff auf das DOM eines Rahmens.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="8b9e0-114">Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="8b9e0-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8b9e0-115">Beschreibt, wie Member des zugrunde liegenden DOM zuzugreifen, die nicht über eine verwaltete Entsprechung verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8b9e0-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="8b9e0-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="8b9e0-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8b9e0-117">Related Sections</span></span>  
 [<span data-ttu-id="8b9e0-118">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8b9e0-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b9e0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b9e0-119">See Also</span></span>  
 [<span data-ttu-id="8b9e0-120">Über das DHTML-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="8b9e0-120">About the DHTML Object Model</span></span>](https://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
