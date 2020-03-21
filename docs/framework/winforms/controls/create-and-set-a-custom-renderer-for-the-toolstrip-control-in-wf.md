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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="14903-102">Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14903-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="14903-103"><xref:System.Windows.Forms.ToolStrip>Steuerelemente unterstützen Themen und Stile leicht.</span><span class="sxs-lookup"><span data-stu-id="14903-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="14903-104">Sie können ein vollständig benutzerdefiniertes Erscheinungsbild und Verhalten <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> (Look <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> and Feel) erzielen, indem Sie entweder die Eigenschaft oder die Eigenschaft auf einen benutzerdefinierten Renderer festlegen.</span><span class="sxs-lookup"><span data-stu-id="14903-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="14903-105">Sie können renderer jedem <xref:System.Windows.Forms.ToolStrip>einzelnen <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.StatusStrip> , oder Steuerelement zuweisen, oder Sie können <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> die <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>Eigenschaft verwenden, um alle Objekte zu beeinflussen, indem Sie die Eigenschaft auf festlegen.</span><span class="sxs-lookup"><span data-stu-id="14903-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14903-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur dann <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> zurück, `null`wenn der Wert von nicht ist.</span><span class="sxs-lookup"><span data-stu-id="14903-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="14903-107">So erstellen Sie einen benutzerdefinierten Renderer</span><span class="sxs-lookup"><span data-stu-id="14903-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="14903-108">Erweitern <xref:System.Windows.Forms.ToolStripRenderer> Sie die Klasse.</span><span class="sxs-lookup"><span data-stu-id="14903-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="14903-109">Implementieren Sie das gewünschte benutzerdefinierte Rendering, indem Sie entsprechende *On...*</span><span class="sxs-lookup"><span data-stu-id="14903-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="14903-110">members</span><span class="sxs-lookup"><span data-stu-id="14903-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="14903-111">So legen Sie fest, dass der benutzerdefinierte Renderer der aktuelle Renderer ist</span><span class="sxs-lookup"><span data-stu-id="14903-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="14903-112">Um den benutzerdefinierten Renderer für einen <xref:System.Windows.Forms.ToolStrip>festzulegen, legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft auf den benutzerdefinierten Renderer fest.</span><span class="sxs-lookup"><span data-stu-id="14903-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="14903-113">Oder um den benutzerdefinierten <xref:System.Windows.Forms.ToolStrip> Renderer für alle In <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> der Anwendung enthaltenen Klassen <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> festzulegen: <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Legen Sie die Eigenschaft auf den benutzerdefinierten Renderer fest, und legen Sie die Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="14903-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="14903-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14903-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="14903-115">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="14903-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="14903-116">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="14903-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="14903-117">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="14903-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
