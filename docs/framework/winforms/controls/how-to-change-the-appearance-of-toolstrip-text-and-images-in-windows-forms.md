---
title: "Gewusst wie: Ändern der Darstellung von ToolStrip-Text und -Bildern in Windows Forms"
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
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d926ce74db9723b6248dbb123513ca38d4adb1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="5d071-102">Gewusst wie: Ändern der Darstellung von ToolStrip-Text und -Bildern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d071-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="5d071-103">Sie können steuern, ob Text und Bilder angezeigt werden eine <xref:System.Windows.Forms.ToolStripItem> und wie sie relativ zueinander ausgerichtet sind und die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="5d071-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="5d071-104">Definieren Sie die Anzeige auf einem ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5d071-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="5d071-105">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="5d071-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="5d071-106">Mögliche Werte sind `Image`, `ImageAndText`, `None`, und `Text`.</span><span class="sxs-lookup"><span data-stu-id="5d071-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="5d071-107">Die Standardeinstellung ist `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="5d071-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="5d071-108">Ausrichten von Text auf einem ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="5d071-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="5d071-109">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="5d071-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="5d071-110">Mögliche Werte sind eine beliebige Kombination von Top, Middle und unten mit Links, zentriert und rechts.</span><span class="sxs-lookup"><span data-stu-id="5d071-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="5d071-111">Die Standardeinstellung ist `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="5d071-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="5d071-112">Um ein Bild auf einem ToolStripItem auszurichten.</span><span class="sxs-lookup"><span data-stu-id="5d071-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="5d071-113">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="5d071-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="5d071-114">Mögliche Werte sind eine beliebige Kombination von Top, Middle und unten mit Links, zentriert und rechts.</span><span class="sxs-lookup"><span data-stu-id="5d071-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="5d071-115">Die Standardeinstellung ist `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="5d071-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="5d071-116">Definieren, wie im Verhältnis zueinander ToolStripItem-Text und Bilder angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="5d071-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="5d071-117">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="5d071-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="5d071-118">Mögliche Werte sind `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, und `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="5d071-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="5d071-119">Die Standardeinstellung ist `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="5d071-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d071-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d071-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="5d071-121">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5d071-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="5d071-122">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5d071-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="5d071-123">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="5d071-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
