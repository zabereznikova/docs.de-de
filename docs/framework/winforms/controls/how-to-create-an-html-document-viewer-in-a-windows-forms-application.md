---
title: Erstellen eines HTML-Dokument-Viewers in einer Windows Forms-App
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732844"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="6eb0c-102">Gewusst wie: Erstellen eines HTML-Dokumentviewers in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6eb0c-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="6eb0c-103">Sie können das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verwenden, um HTML-Dokumente anzuzeigen und zu drucken, ohne die vollständige Funktionalität eines Internet-Webbrowsers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="6eb0c-104">Dies ist hilfreich, wenn Sie die Formatierungsfunktionen von HTML nutzen möchten, aber nicht möchten, dass Benutzer beliebige Webseiten laden, die möglicherweise nicht vertrauenswürdige websteuer Elemente oder potenziell bösartigen Skriptcode enthalten.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="6eb0c-105">Möglicherweise möchten Sie die Funktionalität des <xref:System.Windows.Forms.WebBrowser>-Steuer Elements auf diese Weise einschränken, um es z. b. als HTML-e-Mail-Viewer zu verwenden oder um HTML-formatierte Hilfe in der Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="6eb0c-106">So erstellen Sie einen HTML-Dokument-Viewer</span><span class="sxs-lookup"><span data-stu-id="6eb0c-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="6eb0c-107">Legen Sie die <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>-Eigenschaft auf `false` fest, um zu verhindern, dass das <xref:System.Windows.Forms.WebBrowser> Steuerelement Dateien öffnet, die auf diesem</span><span class="sxs-lookup"><span data-stu-id="6eb0c-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="6eb0c-108">Legen Sie die <xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft auf den Speicherort der anzuzeigenden anfangs Datei fest.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6eb0c-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6eb0c-109">Compiling the Code</span></span>  
 <span data-ttu-id="6eb0c-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6eb0c-110">This example requires:</span></span>  
  
- <span data-ttu-id="6eb0c-111">Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="6eb0c-112">Verweise auf die Assemblys `System` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="6eb0c-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb0c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eb0c-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="6eb0c-114">Übersicht über das WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6eb0c-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="6eb0c-115">WebBrowser-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6eb0c-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="6eb0c-116">Gewusst wie: Navigieren zu einer URL mit dem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6eb0c-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="6eb0c-117">Gewusst wie: Drucken mit einem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6eb0c-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
