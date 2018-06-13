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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds „Datei“
Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows, die die Anwendung ausgeführt wird. Wenn eine Anwendung, die erstellt wurde die [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oder früher wird auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten. Ab der [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], können Sie die automatische Aktualisierung anzuzeigenden abwählen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab  
  
1.  Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FileDialog>
