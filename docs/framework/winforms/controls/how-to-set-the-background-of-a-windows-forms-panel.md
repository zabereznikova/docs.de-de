---
title: Festlegen des Hintergrunds eines Bereichs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744746"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs
Ein Windows Forms <xref:System.Windows.Forms.Panel> Steuerelement kann sowohl eine Hintergrundfarbe als auch ein Hintergrundbild anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft legt die Hintergrundfarbe für die enthaltenen Steuerelemente fest, z. b. Bezeichnungen und Options Felder. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft nicht festgelegt ist, wird der gesamte Bereich durch die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl aufgefüllt. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft festgelegt ist, wird das Bild hinter den enthaltenen Steuerelementen angezeigt.  
  
### <a name="to-set-the-background-programmatically"></a>So legen Sie den Hintergrundprogramm gesteuert fest  
  
1. Legen Sie die <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft des Bereichs auf einen Wert vom Typ <xref:System.Drawing.Color?displayProperty=nameWithType>fest.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Legen Sie die <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft des Panels mithilfe der <xref:System.Drawing.Image.FromFile%2A>-Methode der <xref:System.Drawing.Image?displayProperty=nameWithType>-Klasse fest.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel-Steuerelement](panel-control-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
