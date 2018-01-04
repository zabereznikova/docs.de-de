---
title: "Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed78a49119c87c52a07cc2ade030e66087d3f420
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="25860-102">Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="25860-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="25860-103">Die Bereiche von den <xref:System.Windows.Forms.SplitContainer> Steuerelement eignen sich gut für wird ein, angepasst und von Benutzern bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="25860-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="25860-104">Es werden jedoch Situationen wird den Splitter programmgesteuert –, wo es positioniert ist, und in welchem Maß sie verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="25860-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="25860-105">Die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft und die anderen Eigenschaften auf die <xref:System.Windows.Forms.SplitContainer> steuern das Verhalten der Benutzeroberfläche an Ihre Bedürfnisse genaue zu steuern.</span><span class="sxs-lookup"><span data-stu-id="25860-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="25860-106">Diese Eigenschaften sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="25860-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="25860-107">name</span><span class="sxs-lookup"><span data-stu-id="25860-107">Name</span></span>|<span data-ttu-id="25860-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25860-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="25860-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="25860-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="25860-110">Bestimmt, ob der Splitter mithilfe der Tastatur oder Maus verschiebbar ist.</span><span class="sxs-lookup"><span data-stu-id="25860-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="25860-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="25860-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="25860-112">Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.</span><span class="sxs-lookup"><span data-stu-id="25860-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="25860-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="25860-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="25860-114">Bestimmt die minimale Entfernung in Pixel, dass der Splitter vom Benutzer verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="25860-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="25860-115">Im folgenden Beispiel ändert die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft zum Erstellen eines Effekts "Andocken Splitter"; der Benutzer des Splitters inkrementiert in Schritten von 10 Pixel anstatt der Standardeinstellung 1.</span><span class="sxs-lookup"><span data-stu-id="25860-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="25860-116">SplitContainer-Resize-Verhalten definieren</span><span class="sxs-lookup"><span data-stu-id="25860-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="25860-117">Legen Sie in einer Prozedur, die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft auf die gewünschte Größe, damit das Verhalten "andocken" des Splitters erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="25860-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="25860-118">Im folgenden Codebeispiel wird innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer> Steuerelements springen 10 Pixel beim gezogen festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25860-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="25860-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="25860-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="25860-120">Den Splitter etwas nach links oder rechts verschieben, müssen keine messbaren Auswirkungen; Wenn der Mauszeiger die Form 10 Pixel in beide Richtungen ist, wird der Splitter an die neue Position ausrichten.</span><span class="sxs-lookup"><span data-stu-id="25860-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25860-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25860-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
