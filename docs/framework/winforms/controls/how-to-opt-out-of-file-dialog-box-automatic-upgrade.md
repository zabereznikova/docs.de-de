---
title: 'Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds „Datei“'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 380f8abe502c37e57207c43696158c1e3bdc7697
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532486"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="12cae-102">Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds „Datei“</span><span class="sxs-lookup"><span data-stu-id="12cae-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="12cae-103">Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows, die die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12cae-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="12cae-104">Wenn eine Anwendung, die erstellt wurde die [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oder früher wird auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="12cae-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="12cae-105">Ab der [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], können Sie die automatische Aktualisierung anzuzeigenden abwählen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="12cae-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="12cae-106">So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab</span><span class="sxs-lookup"><span data-stu-id="12cae-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="12cae-107">Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="12cae-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cae-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12cae-108">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>
