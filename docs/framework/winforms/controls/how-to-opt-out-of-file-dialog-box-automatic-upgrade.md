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
ms.openlocfilehash: e12134768d41589dedbeb5a00cab4244c7324f97
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722621"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Vorgehensweise: Ablehnen des automatischen Upgrades des Dialogfelds „Datei“
Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen, die in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows auf die Anwendung ausgeführt wird. Wenn eine Anwendung, die erstellt wurde die [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oder weiter oben angezeigt wird, auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten. Ab .NET Framework 3.0, Sie können die automatische Aktualisierung ablehnen zum Anzeigen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab  
  
1. Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FileDialog>
