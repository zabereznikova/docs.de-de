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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="1b08a-102">Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b08a-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="1b08a-103"><xref:System.Windows.Forms.ToolStrip>Steuerelemente erleichtern die Unterstützung von Designs und Stilen.</span><span class="sxs-lookup"><span data-stu-id="1b08a-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="1b08a-104">Sie können ein vollständiges benutzerdefiniertes Aussehen und Verhalten (Aussehen und Verhalten) erzielen <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> , indem Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> entweder die-Eigenschaft oder die-Eigenschaft auf einen benutzerdefinierten Renderer festlegen.</span><span class="sxs-lookup"><span data-stu-id="1b08a-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="1b08a-105">Sie <xref:System.Windows.Forms.ToolStrip>können jedem einzelnen- <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.MenuStrip>-,-oder <xref:System.Windows.Forms.StatusStrip> -Steuerelement Renderer zuweisen, oder Sie können <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> die-Eigenschaft verwenden, um alle- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> Objekte zu beeinflussen, indem Sie die-Eigenschaft auf <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>festlegen.</span><span class="sxs-lookup"><span data-stu-id="1b08a-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b08a-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur dann zurück, wenn <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> der Wert `null`von nicht ist.</span><span class="sxs-lookup"><span data-stu-id="1b08a-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="1b08a-107">So erstellen Sie einen benutzerdefinierten Renderer</span><span class="sxs-lookup"><span data-stu-id="1b08a-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="1b08a-108">Erweitern Sie <xref:System.Windows.Forms.ToolStripRenderer> die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1b08a-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="1b08a-109">Implementieren Sie das gewünschte benutzerdefinierte Rendering, indem Sie die entsprechenden Optionen *überschreiben.*</span><span class="sxs-lookup"><span data-stu-id="1b08a-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="1b08a-110">Member</span><span class="sxs-lookup"><span data-stu-id="1b08a-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="1b08a-111">So legen Sie den benutzerdefinierten Renderer als aktuellen Renderer fest</span><span class="sxs-lookup"><span data-stu-id="1b08a-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="1b08a-112">Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip>festzulegen, <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> legen Sie die-Eigenschaft auf den benutzerdefinierten Renderer fest.</span><span class="sxs-lookup"><span data-stu-id="1b08a-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="1b08a-113">Oder, um den benutzerdefinierten Renderer für <xref:System.Windows.Forms.ToolStrip> alle in der Anwendung enthaltenen Klassen festzulegen: Legen Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> die-Eigenschaft auf den benutzerdefinierten Renderer <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> und legen <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Sie die-Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="1b08a-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b08a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b08a-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="1b08a-115">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b08a-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="1b08a-116">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="1b08a-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="1b08a-117">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="1b08a-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
