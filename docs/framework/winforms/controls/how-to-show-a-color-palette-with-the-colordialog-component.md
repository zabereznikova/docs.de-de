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
ms.openlocfilehash: 34da70280ff6e5b850469e7ba041cc7c7aaf1f47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637124"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="b122b-102">Vorgehensweise: Anzeigen einer Farbpalette mit der ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b122b-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="b122b-103">Die [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) Komponente zeigt eine Palette von Farben und gibt eine Eigenschaft, die mit der Farbe, die der Benutzer ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="b122b-103">The [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="b122b-104">Wählen Sie eine Farbe, die mit der ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b122b-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="b122b-105">Anzeigen des Dialogfelds mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b122b-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="b122b-106">Verwenden der <xref:System.Windows.Forms.DialogResult> Eigenschaft, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b122b-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="b122b-107">Verwenden der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft der <xref:System.Windows.Forms.ColorDialog> Komponente, um die ausgewählte Farbe festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b122b-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="b122b-108">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler öffnet eine <xref:System.Windows.Forms.ColorDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b122b-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="b122b-109">Wenn eine Farbe ausgewählt, und der Benutzer klickt **OK**, <xref:System.Windows.Forms.Button> Hintergrundfarbe des Steuerelements auf die ausgewählte Farbe festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b122b-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="b122b-110">Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> Steuerelement und ein <xref:System.Windows.Forms.ColorDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b122b-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="b122b-111">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b122b-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b122b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b122b-112">See also</span></span>
- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="b122b-113">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b122b-113">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
