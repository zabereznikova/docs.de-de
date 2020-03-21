---
title: 'Gewusst wie: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: a9f603efdb4b4a5f68154da9c6a8bd05b55b8f46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182223"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a>Gewusst wie: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements
Die <xref:System.Windows.Forms.ToolStrip>-Steuerelemente verfügen über die folgenden zugeordneten Renderingklassen (Zeichnungsklassen):  
  
- <xref:System.Windows.Forms.ToolStripSystemRenderer> stellt das Aussehen und den Stil des Betriebssystems bereit.  
  
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> stellt das Aussehen und den Stil von Microsoft Office bereit.  
  
- <xref:System.Windows.Forms.ToolStripRenderer> ist die abstrakte Basisklasse für die beiden anderen Renderingklassen.  
  
 Zum benutzerdefinierten Zeichnen (auch als Ownerdrawn bekannt) eines <xref:System.Windows.Forms.ToolStrip> können Sie eine der Renderingklassen überschreiben und einen Aspekt der Renderinglogik ändern.  
  
 In den folgenden Verfahren werden verschiedene Aspekte des benutzerdefinierten Zeichnens beschrieben.  
  
### <a name="to-switch-between-the-provided-renderers"></a>So wechseln Sie zwischen den bereitgestellten Renderern  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>-Eigenschaft auf den gewünschten <xref:System.Windows.Forms.ToolStripRenderMode>-Wert fest.  
  
     Mit <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> bestimmt der statische <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> den Renderer für die Anwendung. Die anderen Werte von <xref:System.Windows.Forms.ToolStripRenderMode> lauten <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> und <xref:System.Windows.Forms.ToolStripRenderMode.System>.  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a>So ändern Sie die Rahmen im Stil von Microsoft Office in "gerade"  
  
- Überschreiben Sie <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, rufen Sie jedoch nicht die Basisklasse auf.  
  
> [!NOTE]
> Für <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> gibt es eine Version dieser Methode.  
  
### <a name="to-change-the-professionalcolortable"></a>So ändern Sie die ProfessionalColorTable  
  
- Überschreiben Sie <xref:System.Windows.Forms.ProfessionalColorTable>, und ändern Sie die gewünschten Farben.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a>So ändern Sie das Rendering für alle ToolStrip-Steuerelemente in Ihrer Anwendung  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType>-Eigenschaft, um einen der bereitgestellten Renderer auszuwählen.  
  
2. Verwenden Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>, um einen benutzerdefinierten Renderer zuzuweisen.  
  
3. Stellen Sie sicher, dass <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> auf den Standardwert von <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> festgelegt ist.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a>So deaktivieren Sie die Microsoft Office-Farben für die gesamte Anwendung  
  
- Legen Sie <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> auf `false` fest.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a>So deaktivieren Sie die Microsoft Office-Farben für ein ToolStrip-Steuerelement  
  
- Verwenden Sie ähnlichen Code wie im folgenden Codebeispiel.  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [Steuerelemente mit integrierter Ownerdrawing-Unterstützung](controls-with-built-in-owner-drawing-support.md)
- [Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
