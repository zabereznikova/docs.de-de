---
title: 'Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement'
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
ms.openlocfilehash: f6cb26ff247bba75cc351d453314bade2d38d9f5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144837"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="6ed5a-102">Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6ed5a-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="6ed5a-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie das- <xref:System.Windows.Forms.WebBrowser> Steuerelement zu einer bestimmten URL navigieren.</span><span class="sxs-lookup"><span data-stu-id="6ed5a-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="6ed5a-104">Behandeln Sie das-Ereignis, um zu bestimmen, wann das neue Dokument vollständig geladen wurde <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> .</span><span class="sxs-lookup"><span data-stu-id="6ed5a-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="6ed5a-105">Eine Demonstration dieses Ereignisses finden Sie unter Gewusst [wie: Drucken mit einem Webbrowser-Steuer](how-to-print-with-a-webbrowser-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="6ed5a-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="6ed5a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ed5a-106">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="6ed5a-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6ed5a-107">Compiling the Code</span></span>
 <span data-ttu-id="6ed5a-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6ed5a-108">This example requires:</span></span>

- <span data-ttu-id="6ed5a-109">Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="6ed5a-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="6ed5a-110">Verweise auf die Assemblys `System` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="6ed5a-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ed5a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ed5a-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="6ed5a-112">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6ed5a-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="6ed5a-113">Vorgehensweise: Drucken mit einem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6ed5a-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
