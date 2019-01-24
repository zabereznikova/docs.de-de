---
title: 'Vorgehensweise: Datei Aktualisierung des Dialogfelds automatisch aktivieren'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 7b0c382ca217e9507b0fc7f99953fe2ef0346527
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691384"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="61758-102">Vorgehensweise: Datei Aktualisierung des Dialogfelds automatisch aktivieren</span><span class="sxs-lookup"><span data-stu-id="61758-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="61758-103">Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen, die in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows auf die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61758-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="61758-104">Wenn eine Anwendung, die erstellt wurde die [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oder weiter oben angezeigt wird, auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="61758-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="61758-105">Ab der [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], können Sie die automatische Aktualisierung anzuzeigende Deaktivieren der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="61758-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="61758-106">So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab</span><span class="sxs-lookup"><span data-stu-id="61758-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="61758-107">Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="61758-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61758-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61758-108">See also</span></span>
- <xref:System.Windows.Forms.FileDialog>
