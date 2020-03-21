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
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="0eac6-102">Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="0eac6-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="0eac6-103">Die [ColorDialog-Komponente](colordialog-component-windows-forms.md) zeigt eine Farbpalette an und gibt eine Eigenschaft zurück, die die vom Benutzer ausgewählte Farbe enthält.</span><span class="sxs-lookup"><span data-stu-id="0eac6-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="0eac6-104">So wählen Sie eine Farbe mit der ColorDialog-Komponente aus</span><span class="sxs-lookup"><span data-stu-id="0eac6-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="0eac6-105">Zeigen Sie das <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Dialogfeld mit der Methode an.</span><span class="sxs-lookup"><span data-stu-id="0eac6-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="0eac6-106">Verwenden <xref:System.Windows.Forms.DialogResult> Sie die Eigenschaft, um zu bestimmen, wie das Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0eac6-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="0eac6-107">Verwenden <xref:System.Windows.Forms.ColorDialog.Color%2A> Sie die <xref:System.Windows.Forms.ColorDialog> Eigenschaft der Komponente, um die ausgewählte Farbe festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0eac6-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="0eac6-108">Im folgenden Beispiel <xref:System.Windows.Forms.Button> öffnet der <xref:System.Windows.Forms.Control.Click> Ereignishandler <xref:System.Windows.Forms.ColorDialog> des Steuerelements eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="0eac6-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="0eac6-109">Wenn eine Farbe ausgewählt wird **OK**und der <xref:System.Windows.Forms.Button> Benutzer auf OK klickt, wird die Hintergrundfarbe des Steuerelements auf die ausgewählte Farbe festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0eac6-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="0eac6-110">Im Beispiel wird davon <xref:System.Windows.Forms.Button> ausgegangen, <xref:System.Windows.Forms.ColorDialog> dass das Formular über ein Steuerelement und eine Komponente verfügt.</span><span class="sxs-lookup"><span data-stu-id="0eac6-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="0eac6-111">(Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="0eac6-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0eac6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0eac6-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="0eac6-113">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="0eac6-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
