---
title: "Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b95892641000287f57840ec57cd65147b986829
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form
Mit *einfache Bindung*, können Sie ein einzelnes Datenelement, z. B. einen Spaltenwert in einer Dataset-Tabelle in einem Steuerelement anzuzeigen. Sie können einfache-eine Eigenschaft eines Steuerelements an einen Datenwert binden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-simple-bind-a-control"></a>Simple-eines Steuerelements binden.  
  
1.  Stellen Sie die Verbindung zu einer Datenquelle her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Klicken Sie im Formular, wählen Sie das Steuerelement, und Anzeigen der **Eigenschaften** Fenster.  
  
3.  Erweitern Sie die **(DataBindings)** Eigenschaft.  
  
     Die Eigenschaften, die am häufigsten gebunden werden angezeigt, darunter die **(DataBindings)** Eigenschaft. Beispielsweise ist in den meisten Steuerelementen die **Text** am häufigsten Eigenschaft gebunden ist.  
  
4.  Die Eigenschaft Sie nach Bedarf Bindung ist nicht der häufig gebundenen Eigenschaften, klicken Sie auf die **Auslassungszeichen** Schaltfläche (![von VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton") ) in der **(Erweitert)** Feld zum Anzeigen der **Formatierung und erweiterte Bindung** Dialogfeld mit einer vollständigen Liste der Eigenschaften dieses Steuerelements.  
  
5.  Wählen Sie die Eigenschaft zu binden, und klicken Sie auf den Dropdownpfeil unter **binden**.  
  
     Nun wird eine Liste verfügbarer Datenquellen angezeigt.  
  
6.  Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden. Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
7.  Klicken Sie auf den Namen des Elements, das gebunden werden soll.  
  
8.  Wenn Sie, in bearbeitet haben der **Formatierung und erweiterte Bindung** (Dialogfeld), klicken Sie auf **OK** wieder die **Eigenschaften** Fenster.  
  
9. Wenn Sie zusätzliche Eigenschaften für das Steuerelement binden möchten, wiederholen Sie Schritte 3 bis 7.  
  
    > [!NOTE]
    >  Da einfach gebundene Steuerelemente nur ein einzelnes Datenelement anzuzeigen, ist es sehr typisch Navigationslogik in einem Windows Form mit einfach gebundenen Steuerelementen eingeschlossen werden sollen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Binding>  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
