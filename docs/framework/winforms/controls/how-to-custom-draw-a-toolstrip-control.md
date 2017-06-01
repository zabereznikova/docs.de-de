---
title: "Gewusst wie: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzerdefiniertes Zeichnen"
  - "Zeichnen, Benutzerdefiniert"
  - "Zeichnen, Besitzer"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Ownerdrawing"
  - "ProfessionalColorTable-Klasse, Überschreiben"
  - "RenderMode-Eigenschaft"
  - "Symbolleisten [Windows Forms], Ändern der Farben"
  - "Symbolleisten [Windows Forms], Benutzerdefiniertes Zeichnen"
  - "ToolStrip-Steuerelement [Windows Forms], Ändern der Farben"
  - "ToolStrip-Steuerelement [Windows Forms], Zeichnen"
  - "ToolStripProfessionalRenderer-Klasse"
  - "ToolStripRenderer-Klasse"
  - "ToolStripRenderMode-Klasse"
  - "ToolStripSystemRenderer-Klasse"
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements
Die <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente verfügen über die folgenden zugeordneten Renderingklassen \(Zeichnungsklassen\):  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> stellt das Aussehen und den Stil des Betriebssystems bereit.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> stellt das Aussehen und den Stil von Microsoft Office bereit.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> ist die abstrakte Basisklasse für die beiden anderen Renderingklassen.  
  
 Zum benutzerdefinierten Zeichnen \(auch als Ownerdrawn bekannt\) eines <xref:System.Windows.Forms.ToolStrip> können Sie eine der Renderingklassen überschreiben und einen Aspekt der Renderinglogik ändern.  
  
 In den folgenden Verfahren werden verschiedene Aspekte des benutzerdefinierten Zeichnens beschrieben.  
  
### So wechseln Sie zwischen den bereitgestellten Renderern  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>\-Eigenschaft auf den gewünschten <xref:System.Windows.Forms.ToolStripRenderMode>\-Wert fest.  
  
     Mit <xref:System.Windows.Forms.ToolStripRenderMode> bestimmt der statische <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> den Renderer für die Anwendung.  Die anderen Werte von <xref:System.Windows.Forms.ToolStripRenderMode> lauten <xref:System.Windows.Forms.ToolStripRenderMode>, <xref:System.Windows.Forms.ToolStripRenderMode> und <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
### So ändern Sie die Rahmen im Stil von Microsoft Office in "gerade"  
  
-   Überschreiben Sie <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=fullName>, rufen Sie jedoch nicht die Basisklasse auf.  
  
> [!NOTE]
>  Für <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> gibt es eine Version dieser Methode.  
  
### So ändern Sie die ProfessionalColorTable  
  
-   Überschreiben Sie <xref:System.Windows.Forms.ProfessionalColorTable>, und ändern Sie die gewünschten Farben.  
  
     \[Visual Basic\]  
  
    ```  
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
  
### So ändern Sie das Rendering für alle ToolStrip\-Steuerelemente in Ihrer Anwendung  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=fullName>\-Eigenschaft, um einen der bereitgestellten Renderer auszuwählen.  
  
2.  Verwenden Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>, um einen benutzerdefinierten Renderer zuzuweisen.  
  
3.  Stellen Sie sicher, dass <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName> auf den Standardwert von <xref:System.Windows.Forms.ToolStripRenderMode> festgelegt ist.  
  
### So deaktivieren Sie die Microsoft Office\-Farben für die gesamte Anwendung  
  
-   Legen Sie <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=fullName> auf `false` fest.  
  
### So deaktivieren Sie die Microsoft Office\-Farben für ein ToolStrip\-Steuerelement  
  
-   Verwenden Sie ähnlichen Code wie im folgenden Codebeispiel.  
  
     \[Visual Basic\]  
  
    ```  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
  
    ```  
  
     \[C\#\]  
  
    ```  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 [Steuerelemente mit integrierter Ownerdrawing\-Unterstützung](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)