---
title: 'Vorgehensweise: Horizontales Teilen eines Fensters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 7ef3fe1210ae42c52a4fd7f23633d6566bc102a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956059"
---
# <a name="how-to-split-a-window-horizontally"></a>Vorgehensweise: Horizontales Teilen eines Fensters
Im folgenden Codebeispiel wird der Splitter, der das <xref:System.Windows.Forms.SplitContainer> -Steuerelement horizontal dividiert.  
  
> [!NOTE]
> Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> -Eigenschaft <xref:System.Windows.Forms.SplitContainer> des-Steuer Elements bestimmt die Richtung des Splitters, nicht des Steuer Elements selbst.  
  
### <a name="to-split-a-window-horizontally"></a>So teilen Sie ein Fenster horizontal  
  
1. Legen Sie in einer Prozedur die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> -Eigenschaft <xref:System.Windows.Forms.SplitContainer> des-Steuer <xref:System.Windows.Forms.Orientation.Horizontal>Elements auf fest.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
