---
title: 'Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms'
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
ms.openlocfilehash: ca1a7444c029632f83b1600e5855a13c83777594
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772904"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms
<xref:System.Windows.Forms.ToolStrip> Steuerelemente ermöglichen die einfache Unterstützung von Designs und Stilen. Sie können die vollkommen benutzerdefinierte Aussehen und Verhalten (Aussehen und Verhalten) erreichen, indem Sie die Einstellung der <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft oder das <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> Eigenschaft, um einen benutzerdefinierten Renderer.  
  
 Sie können jedes einzelne Renderer zuweisen <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, oder <xref:System.Windows.Forms.StatusStrip> -Steuerelement, oder Sie können die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> Eigenschaft, um alle Objekte durch Festlegen der <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur, wenn der Wert des <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> nicht `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Erstellen ein benutzerdefiniertes Renderers  
  
1. Erweitern Sie die <xref:System.Windows.Forms.ToolStripRenderer> Klasse.  
  
2. Implementieren Sie den gewünschten benutzerdefinierten Renderer, durch das Überschreiben die entsprechenden *auf...* Member  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Um den benutzerdefinierten Renderer zum aktuellen Renderer  
  
1. Um den benutzerdefinierten Renderer für eine <xref:System.Windows.Forms.ToolStrip>legen die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft, um den benutzerdefinierten Renderer.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Oder legen Sie den benutzerdefinierten Renderer für alle <xref:System.Windows.Forms.ToolStrip> in Ihrer Anwendung enthaltenen Klassen: Legen Sie die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> Eigenschaft auf den benutzerdefinierten Renderer und legen die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
