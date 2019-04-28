---
title: 'Vorgehensweise: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757624"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="e55db-102">Vorgehensweise: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster</span><span class="sxs-lookup"><span data-stu-id="e55db-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="e55db-103">Die Bereiche von den <xref:System.Windows.Forms.SplitContainer> Steuerelement eignen sich gut für das wird ein, angepasst und die vom Benutzer bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="e55db-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="e55db-104">Es werden jedoch Situationen wird den Splitter programmgesteuert –, wo es positioniert ist und in welchem Ausmaß verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="e55db-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="e55db-105">Die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft und die anderen Eigenschaften auf der <xref:System.Windows.Forms.SplitContainer> -Steuerelement bietet eine präzise Kontrolle über das Verhalten der Benutzeroberfläche an Ihre Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="e55db-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="e55db-106">Diese Eigenschaften sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e55db-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="e55db-107">Name</span><span class="sxs-lookup"><span data-stu-id="e55db-107">Name</span></span>|<span data-ttu-id="e55db-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e55db-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e55db-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e55db-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="e55db-110">Bestimmt, ob der Splitter mithilfe der Tastatur oder Maus verschoben ist.</span><span class="sxs-lookup"><span data-stu-id="e55db-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="e55db-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e55db-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="e55db-112">Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.</span><span class="sxs-lookup"><span data-stu-id="e55db-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="e55db-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e55db-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="e55db-114">Bestimmt die minimale Entfernung in Pixeln, des Splitters vom Benutzer verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e55db-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="e55db-115">Im folgenden Beispiel ändert die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft, um einen Effekt "Andocken Splitter"; zu erstellen, wenn der Benutzer den Splitter zieht, inkrementiert in Einheiten von 10 Pixel und nicht der Standardwert 1.</span><span class="sxs-lookup"><span data-stu-id="e55db-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="e55db-116">Verhalten bei Größenänderung SplitContainer definieren</span><span class="sxs-lookup"><span data-stu-id="e55db-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="e55db-117">Legen Sie in einer Prozedur die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft, um die gewünschte Größe, damit der "springende" Verhalten des Splitters erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="e55db-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="e55db-118">Das folgende Codebeispiel zeigt, innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer> -Steuerelement so eingestellt ist, dass 10 Pixel beim gezogen.</span><span class="sxs-lookup"><span data-stu-id="e55db-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
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
  
     <span data-ttu-id="e55db-119">(Visual C#) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="e55db-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="e55db-120">Den Splitter etwas nach links oder rechts verschieben, wird keine erkennbaren Auswirkungen haben; Wenn der Mauszeiger über 10 Pixel in beide Richtungen überschreitet, wird der Splitter jedoch auf die neue Position ausrichten.</span><span class="sxs-lookup"><span data-stu-id="e55db-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55db-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e55db-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
