---
title: 'Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs'
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
ms.openlocfilehash: 9336be2aebb10e5c0bd0bf4648cae34a3b5fe7c3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300402"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs
Ein Windows Forms <xref:System.Windows.Forms.Panel> Steuerelement kann sowohl eine Hintergrundfarbe und ein Bild als Hintergrund anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für die Steuerelemente, z. B. Beschriftungen oder Optionsfelder fest. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft nicht festgelegt ist, die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl füllt den gesamten Bereich. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft festgelegt ist, wird das Bild hinter den enthaltenen Steuerelementen angezeigt werden.  
  
### <a name="to-set-the-background-programmatically"></a>Um den Hintergrund programmgesteuert festzulegen.  
  
1. Festlegen des Bereichs <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft auf einen Wert vom Typ <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Festlegen des Bereichs <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft mit dem <xref:System.Drawing.Image.FromFile%2A> Methode der <xref:System.Drawing.Image?displayProperty=nameWithType> Klasse.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel-Steuerelement](panel-control-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
