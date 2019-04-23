---
title: 'Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322718"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte
Sie können die Windows-Formulare verwenden <xref:System.Windows.Forms.TabControl> , um andere Steuerelemente in einer strukturierten Weise anzuzeigen. Das folgende Verfahren veranschaulicht das Hinzufügen eine Schaltfläche auf der ersten Registerkarte. Informationen zum Hinzufügen eines Symbols auf die Bezeichnung eine Registerkarte, finden Sie unter [Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Programmgesteuertes Hinzufügen des Steuerelements  
  
1. Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem die <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [TabControl-Steuerelement](tabcontrol-control-windows-forms.md)
- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Vorgehensweise: Deaktivieren von Registerkarten](how-to-disable-tab-pages.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
