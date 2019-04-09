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
ms.openlocfilehash: b42845ab996c0985fe6a48ac588e6d706905faac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195851"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte
Sie können die Windows-Formulare verwenden <xref:System.Windows.Forms.TabControl> , um andere Steuerelemente in einer strukturierten Weise anzuzeigen. Das folgende Verfahren veranschaulicht das Hinzufügen eine Schaltfläche auf der ersten Registerkarte. Informationen zum Hinzufügen eines Symbols auf die Bezeichnung eine Registerkarte, finden Sie unter [Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Programmgesteuertes Hinzufügen des Steuerelements  
  
1.  Verwenden der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem die <xref:System.Windows.Forms.Control.Controls%2A> Eigenschaft <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [TabControl-Steuerelement](tabcontrol-control-windows-forms.md)
- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Vorgehensweise: Deaktivieren von Registerkartenseiten](how-to-disable-tab-pages.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
