---
title: 'Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399325"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes
Windows Forms-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt. Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden. Sie können den Text aber auch mithilfe des Designers festlegen.   Siehe auch [wie: Erstellen Access Keys für Windows Forms-Steuerelemente mithilfe des Designers](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [wie: Festlegen der Text angezeigt, die ein Windows Forms-Steuerelement mithilfe den Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [wie: Festlegen des Images Angezeigt wird, indem Sie eine Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>So legen Sie den von einem Steuerelement angezeigten Text programmgesteuert fest  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.  
  
     Wenn Sie eine unterstrichene Zugriffstaste erstellen möchten, setzen Sie ein kaufmännisches Und-Zeichen (&) vor den Buchstaben der Zugriffstaste.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente. Mit der folgenden Codezeile wird der Text des Menüelements beispielsweise wie folgt festgelegt: "& Now For Something Completely Different":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
