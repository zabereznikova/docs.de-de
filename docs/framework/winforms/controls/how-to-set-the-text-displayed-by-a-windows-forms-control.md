---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes'
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
ms.openlocfilehash: 59570af89e6236e3c13866d45dc5361d52b84274
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308522"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes
Windows Forms-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt. Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden. Sie können den Text aber auch mithilfe des Designers festlegen.   Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>So legen Sie den von einem Steuerelement angezeigten Text programmgesteuert fest  
  
1. Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.  
  
     Erstellen Sie eine unterstrichene Zugriffstaste, ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die den Zugriffsschlüssel.  
  
2. Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.  
  
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
    >  Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente. Beispielsweise legt die folgende Codezeile des Menüelements zu lesenden Texts "& Now For Something völlig anderen":  
  
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

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
