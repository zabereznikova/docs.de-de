---
title: 'Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 74947e529a472c9e9a681fcb436ce8aff990c0af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640406"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt
Die Windows-Formulare <xref:System.Windows.Forms.Label> Steuerelement kann ein- oder mehrzeiligen sein und können werden entweder eine feste Größe oder selbst umfassen können automatisch angepasst. Die <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft können Sie die Steuerelemente entsprechend vergrößert oder verkleinert Beschriftungen, die Größe der ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Um ein Bezeichnungsfeld-Steuerelement, das Ändern der Größe dynamisch an dessen Inhalt angepasst zu machen.  
  
1.  Legen Sie dessen <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft `true`.  
  
 Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> nastaven NA hodnotu `false`, im angegebenen Wörter enthalten die <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft möglichst auf die nächste Zeile umbrochen, aber das Steuerelement wird nicht vergrößert.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Übersicht über das Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
