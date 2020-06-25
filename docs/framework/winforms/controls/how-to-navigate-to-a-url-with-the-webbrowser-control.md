---
title: 'Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement'
description: Erfahren Sie, wie Sie das Windows Forms WebBrowser. Navigate-Steuerelement verwenden, um zu einer bestimmten URL zu navigieren. Erfahren Sie außerdem, wie Sie bestimmen, wann das neue Dokument geladen wird.
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
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325577"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="b1179-104">Vorgehensweise: Navigieren zu einem URL mit dem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1179-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="b1179-105">Im folgenden Codebeispiel wird veranschaulicht, wie Sie das- <xref:System.Windows.Forms.WebBrowser> Steuerelement zu einer bestimmten URL navigieren.</span><span class="sxs-lookup"><span data-stu-id="b1179-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="b1179-106">Behandeln Sie das-Ereignis, um zu bestimmen, wann das neue Dokument vollständig geladen wurde <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> .</span><span class="sxs-lookup"><span data-stu-id="b1179-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="b1179-107">Eine Demonstration dieses Ereignisses finden Sie unter Gewusst [wie: Drucken mit einem Webbrowser-Steuer](how-to-print-with-a-webbrowser-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="b1179-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1179-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1179-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="b1179-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b1179-109">Compiling the Code</span></span>
 <span data-ttu-id="b1179-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b1179-110">This example requires:</span></span>

- <span data-ttu-id="b1179-111">Ein <xref:System.Windows.Forms.WebBrowser>-Steuerelement namens `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="b1179-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="b1179-112">Verweise auf die Assemblys `System` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="b1179-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1179-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1179-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="b1179-114">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1179-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="b1179-115">Vorgehensweise: Drucken mit einem WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1179-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
