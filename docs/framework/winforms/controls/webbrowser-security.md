---
title: WebBrowser-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095254"
---
# <a name="webbrowser-security"></a><span data-ttu-id="e365d-102">WebBrowser-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e365d-102">WebBrowser Security</span></span>
<span data-ttu-id="e365d-103">Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement ist nur für vollständige Vertrauenswürdigkeit konzipiert.</span><span class="sxs-lookup"><span data-stu-id="e365d-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="e365d-104">Der im-Steuerelement angezeigte HTML-Inhalt kann von externen Webservern stammen und kann nicht verwalteten Code in Form von Skripts oder websteuer Elementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e365d-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="e365d-105">Wenn Sie in dieser Situation das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verwenden, ist das Steuerelement nicht weniger sicher als Internet Explorer, aber das verwaltete <xref:System.Windows.Forms.WebBrowser> Steuerelement verhindert nicht, dass dieser nicht verwaltete Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e365d-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="e365d-106">Weitere Informationen zu Sicherheitsproblemen im Zusammenhang mit dem zugrunde liegenden ActiveX-`WebBrowser` Steuerelement finden Sie unter [Webbrowser-Steuer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))Element.</span><span class="sxs-lookup"><span data-stu-id="e365d-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e365d-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e365d-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="e365d-108">Übersicht über das WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e365d-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="e365d-109">[WebBrowser-Steuerelement](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e365d-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
