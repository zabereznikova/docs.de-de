---
title: 'Gewusst wie: Positionieren von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6843c22fec964de92c41760f1108d1c83e1f5bf8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083776"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Gewusst wie: Positionieren von Steuerelementen in Windows Forms
Positionieren von Steuerelementen, die Windows Forms-Designer, oder geben Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Um ein Steuerelement auf der Entwurfsoberfläche des Windows Forms-Designers zu positionieren.  
  
-   Ziehen Sie das Steuerelement an die gewünschte Position mit der Maus ein.  
  
    > [!NOTE]
    >  Wählen Sie das Steuerelement, und verschieben Sie, dass es mit dem Pfeil Schlüssel, um genauer zu positionieren. Darüber hinaus *Ausrichtungslinien* unterstützen Sie beim Einfügen von Steuerelementen genauer auf dem Formular. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Um ein Steuerelement, das über das Eigenschaftenfenster zu positionieren.  
  
1.  Klicken Sie auf das Steuerelement platzieren möchten.  
  
2.  In der **Eigenschaften** Fenster Typwerte für die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft, getrennt durch ein Komma, um das Steuerelement innerhalb des Containers zu positionieren.  
  
     Die erste Zahl (X) ist der Abstand vom linken Rand des Containers. die zweite Zahl (Y) wird der Abstand zwischen den oberen Rand des Container-Bereichs, gemessen in Pixel.  
  
    > [!NOTE]
    >  Sie können erweitern die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, um die **X** und **Y** Werte einzeln.  
  
### <a name="to-position-a-control-programmatically"></a>Um ein Steuerelement programmgesteuert zu positionieren.  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des Steuerelements, das eine <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Ändern Sie die X-Koordinate der Position des Steuerelements mit der <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaften.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Um die Position eines Steuerelements programmgesteuerte inkrementieren  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft, um die X-Koordinate des Steuerelements zu erhöhen.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Verwenden der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft festlegen eines Steuerelements X- und Y-Positionen gleichzeitig. Um eine Position einzeln festgelegt werden, verwenden Sie das Steuerelement des <xref:System.Windows.Forms.Control.Left%2A> (**X**) oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**) Untereigenschaften. Versuchen Sie nicht implizit die X- und Y-Koordinaten der Festlegen der <xref:System.Drawing.Point> Struktur, die die Position der Schaltfläche, darstellt, da diese Struktur eine Kopie der Schaltfläche Koordinaten enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Vorgehensweise: Festlegen der Bildschirmposition von Windows Forms](https://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
