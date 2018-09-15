---
title: 'Gewusst wie: Anzeigen der kontextbezogenen Hilfe'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: 47833e734c09e402ab1824b9c629b2ba39acfb9f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45658690"
---
# <a name="how-to-display-pop-up-help"></a>Gewusst wie: Anzeigen der kontextbezogenen Hilfe
Eine Möglichkeit zum Anzeigen von Hilfe in Windows Forms die **Hilfe** Schaltfläche auf der rechten Seite der Titelleiste, über die <xref:System.Windows.Forms.Form.HelpButton%2A> Eigenschaft. Diese Art, die Hilfe aufzurufen, eignet sich besonders für Dialogfelder. In modal (mit der <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode) angezeigten Dialogfeldern ist das Aufrufen externer Hilfesysteme problematisch, da modale Dialogfelder zuerst geschlossen werden müssen, ehe der Fokus auf ein anderes Fenster gerichtet werden kann. Außerdem ist die Verwendung der **Hilfe** Schaltfläche ist erforderlich, dass es ist keine **Minimieren** Schaltfläche oder **Maximieren** Schaltfläche in der Titelleiste angezeigt. Dies ist eine Konvention Dialogfelder, während der Formulare, die in der Regel über **Minimieren** und **Maximieren** Schaltflächen.  
  
 Denken Sie daran, dass Sie Steuerelemente auch mithilfe der <xref:System.Windows.Forms.HelpProvider>-Komponente mit Dateien in einem  Hilfesystem verknüpfen können, selbst wenn Sie kontextbezogene Hilfe implementiert haben. Weitere Informationen finden Sie unter [Bereitstellen von Hilfeinformationen in einer Windows-Anwendung](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-pop-up-help"></a>So zeigen Sie kontextbezogene Hilfe an  
  
1.  Ziehen Sie eine [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) -Komponente aus der Toolbox zu Ihrem Formular.  
  
     Sie befindet sich in der Komponentenleiste im unteren Bereich des Windows Forms Designer.  
  
2.  Legen Sie im Fenster "Eigenschaften" die Eigenschaft <xref:System.Windows.Forms.Form.HelpButton%2A> auf `true` fest. Dadurch wird in der Titelleiste des Formulars auf der rechten Seite eine Schaltfläche mit einem Fragezeichen angezeigt.  
  
3.  Damit die Hilfeschaltfläche <xref:System.Windows.Forms.Form.HelpButton%2A> angezeigt werden kann, müssen Sie die Eigenschaften <xref:System.Windows.Forms.Form.MinimizeBox%2A> und <xref:System.Windows.Forms.Form.MaximizeBox%2A> des Formulars auf `false`, die Eigenschaft <xref:System.Windows.Forms.Form.ControlBox%2A> auf `true` und die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf einen der folgenden Werte festlegen: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> oder <xref:System.Windows.Forms.FormBorderStyle.Sizable>.  
  
4.  Wählen Sie das Steuerelement aus, für das Sie Hilfeinformationen in Ihrem Formular anzeigen möchten, und legen Sie im Fenster "Eigenschaften" den Hilfetext fest. Dies ist die Zeichenfolge mit Text, der in ein ähnliches Fenster angezeigt wird eine [QuickInfo](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).  
  
5.  Drücken Sie **F5**.  
  
6.  Drücken Sie die **Hilfe** in der Titelleiste auf die Schaltfläche, und klicken Sie auf das Steuerelement auf dem Sie den Hilfetext festgelegt haben.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerführung mithilfe von QuickInfos](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrieren von Benutzerhilfe in Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
