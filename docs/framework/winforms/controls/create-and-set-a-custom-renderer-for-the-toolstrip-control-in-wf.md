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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182402"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms
<xref:System.Windows.Forms.ToolStrip>Steuerelemente unterstützen Themen und Stile leicht. Sie können ein vollständig benutzerdefiniertes Erscheinungsbild und Verhalten <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> (Look <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> and Feel) erzielen, indem Sie entweder die Eigenschaft oder die Eigenschaft auf einen benutzerdefinierten Renderer festlegen.  
  
 Sie können renderer jedem <xref:System.Windows.Forms.ToolStrip>einzelnen <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.StatusStrip> , oder Steuerelement zuweisen, oder Sie können <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> die <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>Eigenschaft verwenden, um alle Objekte zu beeinflussen, indem Sie die Eigenschaft auf festlegen.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur dann <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> zurück, `null`wenn der Wert von nicht ist.  
  
### <a name="to-create-a-custom-renderer"></a>So erstellen Sie einen benutzerdefinierten Renderer  
  
1. Erweitern <xref:System.Windows.Forms.ToolStripRenderer> Sie die Klasse.  
  
2. Implementieren Sie das gewünschte benutzerdefinierte Rendering, indem Sie entsprechende *On...* members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>So legen Sie fest, dass der benutzerdefinierte Renderer der aktuelle Renderer ist  
  
1. Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip>festzulegen, legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft auf den benutzerdefinierten Renderer fest.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Oder um den benutzerdefinierten <xref:System.Windows.Forms.ToolStrip> Renderer für alle In <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> der Anwendung enthaltenen Klassen <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> festzulegen: <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Legen Sie die Eigenschaft auf den benutzerdefinierten Renderer fest, und legen Sie die Eigenschaft auf fest.  
  
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
