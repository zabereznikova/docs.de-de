---
title: 'Vorgehensweise: Anzeigen einer Farbpalette mit der ColorDialog-Komponente'
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
ms.openlocfilehash: fcaf5da9958cf66fb63bd753dc94cba9c10f62f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096035"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Vorgehensweise: Anzeigen einer Farbpalette mit der ColorDialog-Komponente
Die [ColorDialog](colordialog-component-windows-forms.md) Komponente zeigt eine Palette von Farben und gibt eine Eigenschaft, die mit der Farbe, die der Benutzer ausgewählt hat.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Wählen Sie eine Farbe, die mit der ColorDialog-Komponente  
  
1.  Anzeigen des Dialogfelds mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
2.  Verwenden der <xref:System.Windows.Forms.DialogResult> Eigenschaft, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde.  
  
3.  Verwenden der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft der <xref:System.Windows.Forms.ColorDialog> Komponente, um die ausgewählte Farbe festzulegen.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler öffnet eine <xref:System.Windows.Forms.ColorDialog> Komponente. Wenn eine Farbe ausgewählt, und der Benutzer klickt **OK**, <xref:System.Windows.Forms.Button> Hintergrundfarbe des Steuerelements auf die ausgewählte Farbe festgelegt ist. Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> Steuerelement und ein <xref:System.Windows.Forms.ColorDialog> Komponente.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog-Komponente](colordialog-component-windows-forms.md)
