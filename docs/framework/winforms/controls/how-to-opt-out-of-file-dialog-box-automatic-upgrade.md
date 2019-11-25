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
ms.openlocfilehash: bbde260cc7f05226c9b06325b45708e1cde3cf8c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976884"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds „Datei“
Wenn die Klassen <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> in einer Anwendung verwendet werden, hängen die Darstellung und das Verhalten von der Windows-Version ab, auf der die Anwendung ausgeführt wird. Wenn eine Anwendung, die auf dem .NET Framework 2,0 oder früher erstellt wurde, unter Windows Vista angezeigt wird, werden <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> automatisch mit dem Aussehen und Verhalten von Windows Vista angezeigt. Beginnend mit dem .NET Framework 3,0 können Sie das automatische Upgrade ablehnen, um die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem Aussehen und Verhalten im [!INCLUDE[winxp](../../../../includes/winxp-md.md)]Format anzuzeigen.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>So lehnen Sie die automatische Aktualisierung des Dialogfelds „Datei“ ab  
  
1. Legen Sie die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>-Eigenschaft <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> auf `false` fest, bevor Sie das Dialogfeld anzeigen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FileDialog>
