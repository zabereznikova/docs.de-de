---
title: 'Vorgehensweise: Ablehnen des automatischen Upgrades des Dialogfelds „Datei“'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 0753873ac37f26d6503397290ef4603702737a86
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170617"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="b1e83-102">Vorgehensweise: Ablehnen des automatischen Upgrades des Dialogfelds „Datei“</span><span class="sxs-lookup"><span data-stu-id="b1e83-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="b1e83-103">Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen, die in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows auf die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1e83-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="b1e83-104">Wenn eine Anwendung, die auf .NET Framework 2.0 oder früher erstellt wurde angezeigt wird, auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b1e83-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="b1e83-105">Ab .NET Framework 3.0, Sie können die automatische Aktualisierung ablehnen zum Anzeigen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b1e83-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="b1e83-106">So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab</span><span class="sxs-lookup"><span data-stu-id="b1e83-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="b1e83-107">Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1e83-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e83-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1e83-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
