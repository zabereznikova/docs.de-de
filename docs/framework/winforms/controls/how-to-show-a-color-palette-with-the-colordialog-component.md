---
title: 'Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: ea12fe19b6c8c7464f0820267face8a1d66de784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536926"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente
Die [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) Komponente zeigt eine Farbpalette an und gibt eine Eigenschaft mit der Farbe, die der Benutzer ausgewählt hat.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Wählen Sie eine Farbe, mit der ColorDialog-Komponente  
  
1.  Anzeigen des Dialogfelds mit den <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
2.  Verwenden der <xref:System.Windows.Forms.DialogResult> -Eigenschaft können Sie bestimmen, wie das Dialogfeld geschlossen wurde.  
  
3.  Verwenden der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft von der <xref:System.Windows.Forms.ColorDialog> Komponente zum Festlegen der ausgewählten Farbe.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine <xref:System.Windows.Forms.ColorDialog> Komponente. Wenn eine Farbe ausgewählt wurde und der Benutzer klickt **OK**, <xref:System.Windows.Forms.Button> Hintergrundfarbe des Steuerelements auf die ausgewählte Farbe festgelegt ist. Im Beispiel wird vorausgesetzt, das Formular verfügt über eine <xref:System.Windows.Forms.Button> Steuerelement und ein <xref:System.Windows.Forms.ColorDialog> Komponente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
