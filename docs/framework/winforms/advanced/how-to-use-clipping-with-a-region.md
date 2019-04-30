---
title: 'Vorgehensweise: Verwenden von Ausschneiden mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954521"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="5b20a-102">Vorgehensweise: Verwenden von Ausschneiden mit einem Bereich</span><span class="sxs-lookup"><span data-stu-id="5b20a-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="5b20a-103">Eine der Eigenschaften von den <xref:System.Drawing.Graphics> -Klasse ist der Clip-Bereich.</span><span class="sxs-lookup"><span data-stu-id="5b20a-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="5b20a-104">Alle Zeichnungen erreicht, indem ein bestimmten <xref:System.Drawing.Graphics> Objekt ist auf den Ausschneidebereich dieses beschränkt <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b20a-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5b20a-105">Sie können die Clip-Bereich festlegen, durch den Aufruf der <xref:System.Drawing.Graphics.SetClip%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5b20a-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b20a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b20a-106">Example</span></span>  
 <span data-ttu-id="5b20a-107">Das folgende Beispiel erstellt einen Pfad, der ein einzelnes Polygon besteht.</span><span class="sxs-lookup"><span data-stu-id="5b20a-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="5b20a-108">Anschließend erstellt der Code eine Region, die basierend auf diesen Pfad.</span><span class="sxs-lookup"><span data-stu-id="5b20a-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="5b20a-109">Die Region wird zum Übergeben der <xref:System.Drawing.Graphics.SetClip%2A> -Methode der ein <xref:System.Drawing.Graphics> -Objekt, und klicken Sie dann zwei Zeichenfolgen stammen.</span><span class="sxs-lookup"><span data-stu-id="5b20a-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="5b20a-110">Die folgende Abbildung zeigt die abgeschnittenen Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="5b20a-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="5b20a-111">![Clip](./media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="5b20a-111">![Clip](./media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b20a-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5b20a-112">Compiling the Code</span></span>  
 <span data-ttu-id="5b20a-113">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5b20a-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b20a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b20a-114">See also</span></span>

- [<span data-ttu-id="5b20a-115">Bereiche in GDI+</span><span class="sxs-lookup"><span data-stu-id="5b20a-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="5b20a-116">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="5b20a-116">Using Regions</span></span>](using-regions.md)
