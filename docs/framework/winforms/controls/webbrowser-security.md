---
title: WebBrowser-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 730d8f692a44a06ea142bb870bbd961d5983c785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534611"
---
# <a name="webbrowser-security"></a><span data-ttu-id="f0484-102">WebBrowser-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f0484-102">WebBrowser Security</span></span>
<span data-ttu-id="f0484-103">Die <xref:System.Windows.Forms.WebBrowser> Steuerelement soll nur vollständige Vertrauenswürdigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0484-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="f0484-104">Der HTML-Inhalt, der im Steuerelement angezeigte kann von externen Webservern stammen und darf nicht verwalteten Code in Form von Skripts oder Websteuerelementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f0484-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="f0484-105">Bei Verwendung der <xref:System.Windows.Forms.WebBrowser> Steuerelement in diesem Fall kann das Steuerelement ist nicht unsicherer als Internet Explorer, aber die verwaltete werden würde <xref:System.Windows.Forms.WebBrowser> Steuerelement verhindert nicht solcher nicht verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0484-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="f0484-106">Weitere Informationen zu Sicherheitsproblemen im Zusammenhang mit der zugrunde liegenden ActiveX `WebBrowser` steuern, finden Sie unter [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="f0484-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0484-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0484-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="f0484-108">Übersicht über das WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f0484-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="f0484-109">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f0484-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
