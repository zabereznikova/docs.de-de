---
title: 'Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 26bc136ea2b7e5bda4a57c5dad65ec3522efcd3d
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258720"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form
Mit *einfache Bindung*, Sie können ein einzelnes Datenelement, z. B. ein Spaltenwert aus einem Dataset-Tabelle in einem Steuerelement anzeigen. Sie können einfach eine Eigenschaft eines Steuerelements an einen Datenwert binden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-simple-bind-a-control"></a>An einfach ein Steuerelement gebunden werden soll  
  
1.  Stellen Sie die Verbindung zu einer Datenquelle her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Klicken Sie in der Form, wählen Sie das Steuerelement und Anzeigen der **Eigenschaften** Fenster.  
  
3.  Erweitern Sie die **(DataBindings)** Eigenschaft.  
  
     Die am häufigsten gebundenen Eigenschaften werden angezeigt, darunter die **(DataBindings)** Eigenschaft. In den meisten Steuerelementen, z. B. die **Text** -Eigenschaft wird am häufigsten gebunden.  
  
4.  Die Eigenschaft gewünscht Bindung gehört nicht zu den häufig gebundenen Eigenschaften, klicken Sie auf die **Auslassungspunkte** Schaltfläche (![VisualStudioEllipsesButton-bildschirmabbildung](../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton") ) in der **(Erweitert)** anzuzeigen die **Formatierung und erweiterte Bindung** Dialogfeld mit einer vollständigen Liste der Eigenschaften, die für dieses Steuerelement.  
  
5.  Wählen Sie die Eigenschaft, die Sie binden möchten und klicken Sie auf den Dropdownpfeil unter **Bindung**.  
  
     Nun wird eine Liste verfügbarer Datenquellen angezeigt.  
  
6.  Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden. Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
7.  Klicken Sie auf den Namen des Elements, das gebunden werden soll.  
  
8.  Wenn Sie, in bearbeitet haben der **Formatierung und erweiterte Bindung** im Dialogfeld klicken Sie auf **OK** zum Zurückgeben der **Eigenschaften** Fenster.  
  
9. Wenn Sie zusätzliche Eigenschaften für das Steuerelement binden möchten, wiederholen Sie Schritte 3 bis 7.  
  
    > [!NOTE]
    >  Da einfach gebundene Steuerelemente nur ein einzelnes Datenelement angezeigt werden, kommt es häufig vor, ein Windows-Formular mit einfachen datengebundenen Steuerelementen Navigationslogik einschließt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Binding>  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
