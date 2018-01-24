---
title: 'Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c6dd45d2070c77b34c66388b397bb784215654
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer
Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um die Gruppierung anderer Steuerelemente. Es gibt drei Gründe zum Gruppieren von Steuerelementen. Gruppieren von verwandten Form-Elemente für eine klare Benutzeroberfläche visual ist. Ein weiterer Vorteil ist die programmgesteuerte Gruppierung von Optionsfeldern z. B.; die letzte ist für die Steuerelemente zur Entwurfszeit als Einheit verschieben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-group-of-controls"></a>So erstellen eine Gruppe von Steuerelementen  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte der Toolbox auf das Formular.  
  
2.  Fügen Sie weitere Steuerelemente, wenn der Bereich, und Zeichnen im Auswahlbereich aus.  
  
     Wenn Sie vorhandene Steuerelemente verfügen, die in einem Bereich eingeschlossen werden sollen, können Sie wählen Sie alle Steuerelemente, Ausschneiden in die Zwischenablage, wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und fügen Sie sie in der Systemsteuerung. Sie können auch in den Bereich ziehen.  
  
3.  (Optional) Wenn Sie ein Panel einen Rahmen hinzufügen möchten, legen Sie dessen <xref:System.Windows.Forms.BorderStyle> Eigenschaft. Es gibt drei Möglichkeiten zur Auswahl: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, und <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Siehe auch  
 [Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Gewusst wie: Festlegen des Hintergrunds eines Bereichs](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
