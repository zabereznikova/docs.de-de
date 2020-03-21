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
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182106"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs
Ein Windows <xref:System.Windows.Forms.Panel> Forms-Steuerelement kann sowohl eine Hintergrundfarbe als auch ein Hintergrundbild anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für die enthaltenen Steuerelemente fest, z. B. Beschriftungen und Optionsfelder. Wenn <xref:System.Windows.Forms.Control.BackgroundImage%2A> die Eigenschaft nicht <xref:System.Windows.Forms.Control.BackColor%2A> festgelegt ist, füllt die Auswahl das gesamte Bedienfeld aus. Wenn <xref:System.Windows.Forms.Control.BackgroundImage%2A> die Eigenschaft festgelegt ist, wird das Bild hinter den enthaltenen Steuerelementen angezeigt.  
  
### <a name="to-set-the-background-programmatically"></a>So stellen Sie den Hintergrund programmgesteuert ein  
  
1. Legen Sie die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des Bedienfelds auf einen Wert vom Typ <xref:System.Drawing.Color?displayProperty=nameWithType>fest.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Legen Sie die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft <xref:System.Drawing.Image.FromFile%2A> des Bedienfelds mithilfe der Methode der <xref:System.Drawing.Image?displayProperty=nameWithType> Klasse fest.  
  
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
