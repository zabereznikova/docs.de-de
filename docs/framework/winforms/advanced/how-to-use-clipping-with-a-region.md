---
title: 'Gewusst wie: Ausschneiden mit einem Bereich'
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
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 281ae701bc3e5cee38952a05474360019f76a665
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="7edc7-102">Gewusst wie: Ausschneiden mit einem Bereich</span><span class="sxs-lookup"><span data-stu-id="7edc7-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="7edc7-103">Eine der Eigenschaften von der <xref:System.Drawing.Graphics> Klasse ist die Clip-Bereich.</span><span class="sxs-lookup"><span data-stu-id="7edc7-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="7edc7-104">Alle Zeichnungen geschieht, indem eine angegebene <xref:System.Drawing.Graphics> Objekt ist nur für den Ausschneidebereich dieses <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="7edc7-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="7edc7-105">Sie können die Clip-Bereich festlegen, durch Aufrufen der <xref:System.Drawing.Graphics.SetClip%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="7edc7-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7edc7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7edc7-106">Example</span></span>  
 <span data-ttu-id="7edc7-107">Das folgende Beispiel erstellt einen Pfad, der ein einzelnes Polygon besteht.</span><span class="sxs-lookup"><span data-stu-id="7edc7-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="7edc7-108">Anschließend erstellt der Code eine Region, basierend auf diesen Pfad.</span><span class="sxs-lookup"><span data-stu-id="7edc7-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="7edc7-109">Die Region wird zum Übergeben der <xref:System.Drawing.Graphics.SetClip%2A> Methode eine <xref:System.Drawing.Graphics> -Objekt, und klicken Sie dann zwei Zeichenfolgen werden gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7edc7-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="7edc7-110">Die folgende Abbildung zeigt die abgeschnittenen Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="7edc7-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="7edc7-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="7edc7-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7edc7-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7edc7-112">Compiling the Code</span></span>  
 <span data-ttu-id="7edc7-113">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="7edc7-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edc7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7edc7-114">See Also</span></span>  
 [<span data-ttu-id="7edc7-115">Bereiche in GDI+</span><span class="sxs-lookup"><span data-stu-id="7edc7-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="7edc7-116">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="7edc7-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
