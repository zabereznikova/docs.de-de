---
title: Globale und lokale Transformationen
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 432402fefc6c958fbab0b1450a429d9b130b8239
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="a60d2-102">Globale und lokale Transformationen</span><span class="sxs-lookup"><span data-stu-id="a60d2-102">Global and Local Transformations</span></span>
<span data-ttu-id="a60d2-103">Eine globale Transformation ist eine Transformation, die für jedes Element gezeichnet gilt eine bestimmte <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a60d2-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="a60d2-104">Im Gegensatz dazu ist eine lokale Transformation eine Transformation wendet auf ein bestimmtes Element gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a60d2-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="a60d2-105">Globale Transformationen</span><span class="sxs-lookup"><span data-stu-id="a60d2-105">Global Transformations</span></span>  
 <span data-ttu-id="a60d2-106">Um eine globale Transformation zu erstellen, erstellen eine <xref:System.Drawing.Graphics> Objekt aus, und bearbeiten dann seine <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a60d2-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="a60d2-107">Die <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft ist ein <xref:System.Drawing.Drawing2D.Matrix> Objekt, damit es eine beliebige Sequenz von affine Transformationen aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="a60d2-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="a60d2-108">Die Transformation gespeichert, der <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft wird die globale Transformation aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a60d2-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="a60d2-109">Die <xref:System.Drawing.Graphics> -Klasse stellt mehrere Methoden für die Erstellung von einer zusammengesetzten globalen Transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, und <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="a60d2-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="a60d2-110">Im folgende Beispiel zeichnet eine Ellipse zweimal: einmal vor dem Erstellen einer globalen Transformation und einmal nach.</span><span class="sxs-lookup"><span data-stu-id="a60d2-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="a60d2-111">Die Transformation zuerst mit einem Faktor von 0,5 in y-Richtung skaliert und dann 50 Einheiten entlang der x-Achse an übersetzt und dann 30 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="a60d2-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="a60d2-112">Die folgende Abbildung gibt Aufschluss über die Matrizen in der Transformation.</span><span class="sxs-lookup"><span data-stu-id="a60d2-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="a60d2-113">![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="a60d2-113">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a60d2-114">Im vorherigen Beispiel ist die Ellipse den Ursprung des Koordinatensystems, gedreht auf der linken oberen Ecke des Clientbereichs.</span><span class="sxs-lookup"><span data-stu-id="a60d2-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="a60d2-115">Hierdurch wird ein anderes Ergebnis als die Ellipse um ihren Mittelpunkt drehen.</span><span class="sxs-lookup"><span data-stu-id="a60d2-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="a60d2-116">Lokale Transformationen</span><span class="sxs-lookup"><span data-stu-id="a60d2-116">Local Transformations</span></span>  
 <span data-ttu-id="a60d2-117">Eine lokale Transformation gilt für ein bestimmtes Element gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a60d2-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="a60d2-118">Z. B. eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt verfügt über eine <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> Methode, die Ihnen ermöglicht, die Datenpunkten der, dass der Pfad zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="a60d2-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="a60d2-119">Im folgende Beispiel zeichnet ein Rechteck mit keine Transformation und einen Pfad mit eine Drehtransformation an.</span><span class="sxs-lookup"><span data-stu-id="a60d2-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="a60d2-120">(Wird davon ausgegangen Sie, dass keine globalen Transformation vorhanden ist.)</span><span class="sxs-lookup"><span data-stu-id="a60d2-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="a60d2-121">Sie können die globale Transformation mit lokalen Transformationen, um eine Vielzahl von Ergebnisse zu erzielen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="a60d2-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="a60d2-122">Beispielsweise können Sie die globale Transformation für das Koordinatensystem überarbeiten und lokale Transformationen zum Drehen und Skalieren von Objekten, die auf das neue Koordinatensystem gezeichnet verwenden.</span><span class="sxs-lookup"><span data-stu-id="a60d2-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="a60d2-123">Angenommen Sie, Sie einem Koordinatensystem möchten, die seine Ursprung 200 Pixel vom linken Rand des Clientbereichs und 150 Pixel vom oberen Rand des Clientbereichs verfügt.</span><span class="sxs-lookup"><span data-stu-id="a60d2-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="a60d2-124">Darüber hinaus wird davon ausgegangen Sie, dass das Pixel, mit der x-Achse nach rechts und die y-Achse nach oben zeigen als Maßeinheit verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a60d2-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="a60d2-125">Das Standard-Koordinatensystem ist die y-Achse nach unten, zeigen, sodass Sie eine Spiegelung entlang der horizontalen Achse durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="a60d2-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="a60d2-126">Die folgende Abbildung zeigt die Matrix für eine solche Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="a60d2-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="a60d2-127">![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="a60d2-127">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="a60d2-128">Als Nächstes wird davon ausgegangen Sie, dass Sie eine 200 Übersetzungseinheiten rechts und 150 Einheiten nach unten durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="a60d2-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="a60d2-129">Im folgende Beispiel wird das Koordinatensystem, die eben beschriebene durch die globale Transformation für das Festlegen einer <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a60d2-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="a60d2-130">Der folgende Code (am Ende des vorherigen Beispiels platziert) erstellt einen Pfad, der ein einzelnes Rechteck mit der linken unteren Ecke an den Ursprung des Koordinatensystems an die neue besteht.</span><span class="sxs-lookup"><span data-stu-id="a60d2-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="a60d2-131">Das Rechteck wird einmal ohne lokale Transformation und einmal mit lokaler Transformation gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a60d2-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="a60d2-132">Die lokale Transformation besteht eine horizontale Skalierung mit einem Faktor von 2 gefolgt von einer 30 Grad drehen.</span><span class="sxs-lookup"><span data-stu-id="a60d2-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="a60d2-133">Die folgende Abbildung zeigt das neue Koordinatensystem und den zwei Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="a60d2-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="a60d2-134">![Transformationen](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="a60d2-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60d2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a60d2-135">See Also</span></span>  
 [<span data-ttu-id="a60d2-136">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="a60d2-136">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="a60d2-137">Verwenden von Transformationen in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="a60d2-137">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
