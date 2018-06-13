---
title: 'Gewusst wie: Navigieren zu einem URL mit dem WebBrowser-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: f34577d45ddfbd2445fd4558c5694facf3f1aa29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531884"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="08860-102">Gewusst wie: Navigieren zu einem URL mit dem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08860-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="08860-103">Im folgenden Codebeispiel wird veranschaulicht, wie zum Navigieren der <xref:System.Windows.Forms.WebBrowser> Steuerelement an eine bestimmte URL.</span><span class="sxs-lookup"><span data-stu-id="08860-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="08860-104">Um zu bestimmen, wann das neue Dokument vollständig geladen ist, behandelt die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="08860-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="08860-105">Eine Demonstration dieses Ereignisses, finden Sie unter [wie: Drucken mit einem WebBrowser-Steuerelement](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="08860-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08860-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08860-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08860-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="08860-107">Compiling the Code</span></span>  
 <span data-ttu-id="08860-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="08860-108">This example requires:</span></span>  
  
-   <span data-ttu-id="08860-109">Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="08860-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="08860-110">Verweise auf die Assemblys `System` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="08860-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08860-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08860-111">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [<span data-ttu-id="08860-112">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08860-112">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [<span data-ttu-id="08860-113">Gewusst wie: Drucken mit einem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="08860-113">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
