---
title: 'Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743411"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms
<xref:System.Windows.Forms.ToolStrip> Steuerelemente erleichtern die Unterstützung von Designs und Stilen. Sie können ein vollständiges benutzerdefiniertes Aussehen und Verhalten (Aussehen und Verhalten) erzielen, indem Sie entweder die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>-Eigenschaft oder die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>-Eigenschaft auf einen benutzerdefinierten Renderer festlegen.  
  
 Sie können jedem einzelnen <xref:System.Windows.Forms.ToolStrip>-, <xref:System.Windows.Forms.MenuStrip>-, <xref:System.Windows.Forms.ContextMenuStrip>-oder <xref:System.Windows.Forms.StatusStrip>-Steuerelement Renderer zuweisen, oder Sie können die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>-Eigenschaft verwenden, um alle Objekte zu beeinflussen, indem Sie die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>festlegen.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur zurück, wenn der Wert von <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> nicht `null`ist.  
  
### <a name="to-create-a-custom-renderer"></a>So erstellen Sie einen benutzerdefinierten Renderer  
  
1. Erweitern Sie die <xref:System.Windows.Forms.ToolStripRenderer>-Klasse.  
  
2. Implementieren Sie das gewünschte benutzerdefinierte Rendering, indem Sie die entsprechenden Optionen *überschreiben.* members  
  
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
  
    ```csharp  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>So legen Sie den benutzerdefinierten Renderer als aktuellen Renderer fest  
  
1. Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip>festzulegen, legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>-Eigenschaft auf den benutzerdefinierten Renderer fest.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Wenn Sie den benutzerdefinierten Renderer für alle in der Anwendung enthaltenen <xref:System.Windows.Forms.ToolStrip> Klassen festlegen möchten, legen Sie die Eigenschaft <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> auf den benutzerdefinierten Renderer fest, und legen Sie die Eigenschaft <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> auf <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>fest.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
