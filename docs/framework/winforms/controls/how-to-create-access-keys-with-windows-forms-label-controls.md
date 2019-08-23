---
title: 'Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen'
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
ms.openlocfilehash: dd7f238f8c20ba990158f23344e36376d3b1cb7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950541"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Vorgehensweise: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen
Windows Forms <xref:System.Windows.Forms.Label> Steuerelemente können verwendet werden, um Zugriffsschlüssel für andere Steuerelemente zu definieren. Wenn Sie in einem Label-Steuerelement eine Zugriffstaste definieren, kann der Benutzer die Alt-Taste sowie das von Ihnen festgelegten Zeichen drücken, um den Fokus in der Aktivier Reihenfolge auf das Steuerelement zu verschieben. Da Bezeichnungen keinen Fokus erhalten können, wechselt der Fokus automatisch zum nächsten Steuerelement in der Aktivier Reihenfolge. Verwenden Sie dieses Verfahren, um Textfeldern, Kombinations Feldern, Listenfeldern und Daten Rastern Zugriffstasten zuzuweisen.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>So weisen Sie einem Steuerelement mit einer Bezeichnung einen Zugriffsschlüssel zu  
  
1. Zeichnen Sie zuerst die Bezeichnung, und zeichnen Sie dann das andere Steuerelement.  
  
     -oder-  
  
     Zeichnen Sie die Steuerelemente in beliebiger Reihen <xref:System.Windows.Forms.Control.TabIndex%2A> Folge, und legen Sie die-Eigenschaft der Bezeichnung auf ein kleiner als das andere Steuerelement fest.  
  
2. Legen Sie die- <xref:System.Windows.Forms.Label.UseMnemonic%2A> Eigenschaft der `true`Bezeichnung auf fest.  
  
3. Verwenden Sie ein kaufmännisches und-Zeichen (&) in <xref:System.Windows.Forms.Label.Text%2A> der-Eigenschaft der Bezeichnung, um den Zugriffsschlüssel für die Bezeichnung zuzuweisen. Weitere Informationen finden Sie unter [Erstellen von Zugriffs Schlüsseln für Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)-Steuerelemente.  
  
    > [!NOTE]
    > Möglicherweise möchten Sie kaufmännische und-Zeichen in einem Label-Steuerelement anzeigen, anstatt Sie zum Erstellen von Zugriffs Schlüsseln zu verwenden. Dies kann vorkommen, wenn Sie ein Label-Steuerelement an ein Feld in einem Recordset binden, in dem die Daten kaufmännische Werte enthalten. Legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> - `false`Eigenschaft auf fest, um kaufmännische Zeichen in einem Label-Steuerelement anzuzeigen. Wenn Sie kaufmännische und auch Zugriffsschlüssel anzeigen möchten, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A> -Eigenschaft auf `true` fest, und geben Sie den Zugriffsschlüssel mit einem kaufmännischen und-Zeichen (&) und dem kaufmännischen und-Zeichen an, um zwei kaufmännische und-Zeichen anzuzeigen.  
  
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

- [Vorgehensweise: Größe eines Windows Forms Label-Steuer Elements an seinen Inhalt anpassen](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Label-Steuerelement](label-control-windows-forms.md)
