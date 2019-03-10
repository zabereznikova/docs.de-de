---
title: 'Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 227880ad15e452df3f05807c41f3923cccb6fe3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708300"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen
Windows Forms <xref:System.Windows.Forms.Label> Steuerelemente können verwendet werden, um die Zugriffstasten für andere Steuerelemente definieren. Wenn Sie einen Zugriffsschlüssel in ein Label-Steuerelement definieren, kann Benutzer drücken, die ALT-Taste plus das Zeichen, das Sie festlegen, um den Fokus auf das Steuerelement zu verschieben, die sie in der Aktivierreihenfolge folgt. Da Bezeichnungen keinen Fokus erhalten können, verschiebt den Fokus automatisch auf das nächste Steuerelement in der Aktivierreihenfolge. Verwenden Sie dieses Verfahren, um Textfelder, Kombinationsfelder, Listenfelder und Datenraster Zugriffsschlüssel zuweisen.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Zuweisen eine Zugriffstaste auf ein Steuerelement mit einer Bezeichnung  
  
1.  Zeichnen Sie zuerst die Bezeichnung, und klicken Sie dann zeichnen Sie das andere Steuerelement zu.  
  
     - oder -   
  
     Zeichnen Sie die Steuerelemente in beliebiger Reihenfolge aus, und legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft der Bezeichnung bis eins weniger als das andere Steuerelement.  
  
2.  Legen Sie die Bezeichnung des <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true`.  
  
3.  Verwenden Sie ein kaufmännisches und-Zeichen (&), in der Bezeichnung <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft, um den Zugriffsschlüssel für die Bezeichnung zuweisen. Weitere Informationen finden Sie unter [Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Sie sollten kaufmännische und-Zeichen in ein Label-Steuerelement anzeigen, anstatt Sie zu verwenden, um Zugriffstasten zu erstellen. Dies kann auftreten, wenn Sie ein Label-Steuerelement an ein Feld in einem Recordset binden, in denen die Daten kaufmännische und-Zeichen enthält. Um das kaufmännische und-Zeichen in ein Label-Steuerelement anzuzeigen, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `false`. Wenn Sie das kaufmännische und-Zeichen anzuzeigen und außerdem einen Zugriffsschlüssel möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft `true` und geben Sie den Zugriffsschlüssel ein kaufmännisches und-Zeichen (&) und dem kaufmännischen und-Zeichen, das mit zwei kaufmännische und-Zeichen angezeigt.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Größe der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Label-Steuerelement](label-control-windows-forms.md)
