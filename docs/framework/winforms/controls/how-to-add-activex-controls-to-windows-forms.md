---
title: 'Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: c851a215638e60642bf93564f4884b5a79d430d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms
Während der Windows Forms-Designer zum Hosten von Windows Forms-Steuerelementen optimiert ist, können Sie auch ActiveX-Steuerelementen in Windows Forms platziert.  
  
> [!CAUTION]
>  Es gibt leistungseinschränkungen für Windows Forms auf, wenn ActiveX-Steuerelemente hinzugefügt werden.  
  
 Bevor Sie ActiveX-Steuerelementen zum Formular hinzufügen, müssen Sie diese zur Toolbox hinzufügen. Weitere Informationen finden Sie unter [COM-Komponenten, Dialogfeld "Toolbox" anpassen](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>So fügen Sie ein ActiveX-Steuerelement zu einem Windows Form hinzu  
  
-   Doppelklicken Sie auf das Steuerelement in der Toolbox.  
  
     Visual Studio fügt alle Verweise auf das Steuerelement im Projekt. Weitere Informationen über die Dinge zu bedenken, wenn mithilfe von ActiveX-Steuerelementen in Windows Forms finden Sie unter [Überlegungen bei der ein ActiveX-Steuerelement in Windows Forms Hosting](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Windows Forms ActiveX Control Importer (AxImp.exe) erstellt Ereignisargumente eines anderen Typs als beim Import von ActiveX-dynamic Link Librarys erwartet. Die Argumente von AxImp.exe erstellt werden wie die folgende: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`Wenn `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` wird erwartet. Denken Sie daran, dass diese Unregelmäßigkeit Code nicht verhindert wird, Normal zu funktionieren. Weitere Informationen finden Sie unter [Windows Forms ActiveX Control Importer-Tool (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
