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
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141782"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente
Die [ColorDialog-Komponente](colordialog-component-windows-forms.md) zeigt eine Farbpalette an und gibt eine Eigenschaft zurück, die die vom Benutzer ausgewählte Farbe enthält.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>So wählen Sie eine Farbe mit der ColorDialog-Komponente aus  
  
1. Zeigen Sie das <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Dialogfeld mit der Methode an.  
  
2. Verwenden <xref:System.Windows.Forms.DialogResult> Sie die Eigenschaft, um zu bestimmen, wie das Dialogfeld geschlossen wurde.  
  
3. Verwenden <xref:System.Windows.Forms.ColorDialog.Color%2A> Sie die <xref:System.Windows.Forms.ColorDialog> Eigenschaft der Komponente, um die ausgewählte Farbe festzulegen.  
  
     Im folgenden Beispiel <xref:System.Windows.Forms.Button> öffnet der <xref:System.Windows.Forms.Control.Click> Ereignishandler <xref:System.Windows.Forms.ColorDialog> des Steuerelements eine Komponente. Wenn eine Farbe ausgewählt wird **OK**und der <xref:System.Windows.Forms.Button> Benutzer auf OK klickt, wird die Hintergrundfarbe des Steuerelements auf die ausgewählte Farbe festgelegt. Im Beispiel wird davon <xref:System.Windows.Forms.Button> ausgegangen, <xref:System.Windows.Forms.ColorDialog> dass das Formular über ein Steuerelement und eine Komponente verfügt.  
  
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
  
     (Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog-Komponente](colordialog-component-windows-forms.md)
