---
title: "Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers f&#252;r das ToolStrip-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbolleisten [Windows Forms], Rendern"
  - "ToolStrip-Steuerelement [Windows Forms], Benutzerdefiniertes Rendering"
  - "ToolStrip-Steuerelement [Windows Forms], Rendern"
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers f&#252;r das ToolStrip-Steuerelement in Windows Forms
<xref:System.Windows.Forms.ToolStrip>\-Steuerelemente ermöglichen die einfache Unterstützung von Designs und Stilen.  Sie können das Aussehen und Verhalten vollständig anpassen, indem Sie entweder die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>\-Eigenschaft oder die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>\-Eigenschaft auf einen benutzerdefinierten Renderer festlegen.  
  
 Sie können Renderer jedem einzelnen Steuerelement vom Typ <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip> oder <xref:System.Windows.Forms.StatusStrip> zuordnen oder die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>\-Eigenschaft verwenden, um alle Objekte anzupassen, indem Sie die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Forms.ToolStripRenderMode?displayProperty=fullName> festlegen.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> gibt nur <xref:System.Windows.Forms.ToolStripRenderMode> zurück, wenn der Wert von <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> nicht `null` lautet.  
  
### So erstellen Sie einen benutzerdefinierten Renderer  
  
1.  Erweitern Sie die <xref:System.Windows.Forms.ToolStripRenderer>\-Klasse.  
  
2.  Implementieren Sie den gewünschten benutzerdefinierten Renderer, indem Sie die entsprechenden *On…*\-Member überschreiben.  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
  
    ```  
  
     \[C\#\]  
  
    ```  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
  
    ```  
  
### So legen Sie den benutzerdefinierten Renderer als aktuellen Renderer fest  
  
1.  Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip> festzulegen, legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>\-Eigenschaft auf den benutzerdefinierten Renderer fest.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.Renderer = new RedTextRenderer();  
  
    ```  
  
2.  Um den benutzerdefinierten Renderer für alle <xref:System.Windows.Forms.ToolStrip>\-Klassen in der Anwendung festzulegen, legen Sie die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>\-Eigenschaft auf den benutzerdefinierten Renderer fest und die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)