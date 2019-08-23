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
ms.openlocfilehash: c354ace3a7d3ce43f549dd1295a85fbee004eb22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929730"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms
<xref:System.Windows.Forms.ToolStrip>Steuerelemente erleichtern die Unterstützung von Designs und Stilen. Sie können ein vollständiges benutzerdefiniertes Aussehen und Verhalten (Aussehen und Verhalten) erzielen <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> , indem Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> entweder die-Eigenschaft oder die-Eigenschaft auf einen benutzerdefinierten Renderer festlegen.  
  
 Sie <xref:System.Windows.Forms.ToolStrip>können jedem einzelnen- <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.MenuStrip>-,-oder <xref:System.Windows.Forms.StatusStrip> -Steuerelement Renderer zuweisen, oder Sie können <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> die-Eigenschaft verwenden, um alle- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> Objekte zu beeinflussen, indem Sie die-Eigenschaft auf <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>festlegen.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur dann zurück, wenn <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> der Wert `null`von nicht ist.  
  
### <a name="to-create-a-custom-renderer"></a>So erstellen Sie einen benutzerdefinierten Renderer  
  
1. Erweitern Sie <xref:System.Windows.Forms.ToolStripRenderer> die-Klasse.  
  
2. Implementieren Sie das gewünschte benutzerdefinierte Rendering, indem Sie die entsprechenden Optionen *überschreiben.* Member  
  
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
  
1. Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip>festzulegen, <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> legen Sie die-Eigenschaft auf den benutzerdefinierten Renderer fest.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Oder, um den benutzerdefinierten Renderer für <xref:System.Windows.Forms.ToolStrip> alle in der Anwendung enthaltenen Klassen festzulegen: Legen Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> die-Eigenschaft auf den benutzerdefinierten Renderer <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> und legen <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Sie die-Eigenschaft auf fest.  
  
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
