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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Vorgehensweise: Ablehnen des automatischen Upgrades des Dialogfelds „Datei“
Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen, die in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows auf die Anwendung ausgeführt wird. Wenn eine Anwendung, die auf .NET Framework 2.0 oder früher erstellt wurde angezeigt wird, auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten. Ab .NET Framework 3.0, Sie können die automatische Aktualisierung ablehnen zum Anzeigen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab  
  
1. Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> zu `false` , bevor Sie das Dialogfeld anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FileDialog>
