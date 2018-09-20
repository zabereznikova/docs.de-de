---
title: WebBrowser-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 683c6ad4cbc55a889f4a0c1d20ebe8e8a2669a13
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46492236"
---
# <a name="webbrowser-security"></a><span data-ttu-id="e7401-102">WebBrowser-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e7401-102">WebBrowser Security</span></span>
<span data-ttu-id="e7401-103">Die <xref:System.Windows.Forms.WebBrowser> dient als voll vertrauenswürdig nur funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e7401-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="e7401-104">Der im Steuerelement angezeigte HTML-Inhalt aus einer externen Webserver und kann nicht verwalteten Codes in Form eines Skripts oder Websteuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7401-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="e7401-105">Bei Verwendung der <xref:System.Windows.Forms.WebBrowser> -Steuerelement in diesem Fall das Steuerelement ist nicht unsicherer als Internet Explorer, aber die verwaltete wäre <xref:System.Windows.Forms.WebBrowser> Steuerelements verhindert nicht solche nicht verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7401-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="e7401-106">Weitere Informationen zu Sicherheitsproblemen, die im Zusammenhang mit der zugrunde liegenden ActiveX `WebBrowser` steuern, finden Sie unter [WebBrowser-Steuerelement](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="e7401-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7401-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7401-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="e7401-108">Übersicht über das WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e7401-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="e7401-109">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e7401-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
