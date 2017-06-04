---
title: "Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds &quot;Datei&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Automatische Aktualisierung ablehnen OpenFileDialog [Windows Forms]"
  - "(Dialogfeld) [Windows Forms], Ablehnen der automatischen Aktualisierung"
  - "Windows Vista-Dateidialogfeld Feld, Ablehnen der automatischen Aktualisierung"
  - "SaveFileDialog [Windows Forms], Ablehnen der automatischen Aktualisierung"
  - "AutoUpgradeEnabled-Eigenschaft"
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Ablehnen der automatischen Aktualisierung des Dialogfelds &quot;Datei&quot;
Wenn die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen in einer Anwendung verwendet werden, deren Darstellung und Verhalten hängt von der Version von Windows, die die Anwendung ausgeführt wird. Wenn eine Anwendung, die erstellt wurde der [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oder früher auf angezeigt [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> werden automatisch angezeigt, mit der [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] Aussehen und Verhalten. Ab der [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], können Sie die automatische Aktualisierung anzuzeigenden Ablehnen der <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> mit einem [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-Erscheinungsbild und Verhalten.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Datei automatische Aktualisierung des Dialogfelds abwählen  
  
1.  Festlegen der <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> -Eigenschaft des <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog> , `false` , bevor Sie das Dialogfeld anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FileDialog>