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
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015825"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="ca683-102">Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca683-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="ca683-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.WebBrowser> das-Steuerelement zu einer bestimmten URL navigieren.</span><span class="sxs-lookup"><span data-stu-id="ca683-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="ca683-104">Behandeln Sie das <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> -Ereignis, um zu bestimmen, wann das neue Dokument vollständig geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ca683-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="ca683-105">Eine Demonstration dieses Ereignisses finden [Sie unter Gewusst wie: Drucken mit einem Webbrowser-](how-to-print-with-a-webbrowser-control.md)Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ca683-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="ca683-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca683-106">Example</span></span>

```vb
Me.webBrowser1.Navigate("http://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("http://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="ca683-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ca683-107">Compiling the Code</span></span>
 <span data-ttu-id="ca683-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ca683-108">This example requires:</span></span>

- <span data-ttu-id="ca683-109">Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="ca683-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="ca683-110">Verweise auf die Assemblys `System` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="ca683-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca683-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca683-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="ca683-112">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca683-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="ca683-113">Vorgehensweise: Drucken mit einem Webbrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca683-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
