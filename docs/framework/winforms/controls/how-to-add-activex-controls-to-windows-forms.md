---
title: 'Vorgehensweise: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166048"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Vorgehensweise: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms
Während der Windows Forms-Designer zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie auch die ActiveX-Steuerelementen in Windows Forms einfügen.  
  
> [!CAUTION]
>  Es gibt leistungseinschränkungen für Windows Forms, wenn ActiveX-Steuerelemente hinzugefügt werden.  
  
 Bevor Sie das ActiveX-Steuerelementen zum Formular hinzufügen, müssen Sie sie zur Toolbox hinzufügen. Weitere Informationen finden Sie unter [COM-Komponenten, Dialogfeld "Toolbox" anpassen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Das Windows-Formular ein ActiveX-Steuerelement hinzu  
  
-   Doppelklicken Sie auf das Steuerelement in der Toolbox.  
  
     Alle Verweise auf das Steuerelement wird von Visual Studio in Ihrem Projekt hinzugefügt. Weitere Informationen zu Dinge zu bedenken, wenn ActiveX-Steuerelementen in Windows Forms verwenden, finden Sie unter [Aspekte beim Hosten eines ActiveX-Steuerelements in einem Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Windows Forms ActiveX Control Importer (AxImp.exe) erstellt die Ereignisargumente, die von einem anderen Typ als beim Import von ActiveX-dynamic Link Librarys erwartet. Die Argumente, die von AxImp.exe erstellt sind ähnlich dem folgenden: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`Wenn `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` wird erwartet. Denken Sie daran, dass diese Unregelmäßigkeit nicht Code verhindert, Normal zu funktionieren. Weitere Informationen finden Sie unter [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
