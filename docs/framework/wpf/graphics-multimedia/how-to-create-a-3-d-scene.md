---
title: 'Gewusst wie: Erstellen einer 3D-Szene'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd84a95bf793b3da9970b605b2f02509e3938ab0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="27402-102">Gewusst wie: Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="27402-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="27402-103">Dieses Beispiel zeigt, wie ein 3D-Objekt erstellt, der eine flache Blatt Papier ähnelt dem gedreht wurde.</span><span class="sxs-lookup"><span data-stu-id="27402-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="27402-104">Ein <xref:System.Windows.Controls.Viewport3D> zusammen mit den folgenden Komponenten werden zum Erstellen dieser einfachen 3D-Szene verwendet:</span><span class="sxs-lookup"><span data-stu-id="27402-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="27402-105">Eine Kamera erstellt, wobei eine <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="27402-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="27402-106">Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="27402-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="27402-107">Ein Netz wird erstellt, um die Form der Verwendung von 3D-Objekt (Blatt Papier) angeben der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="27402-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="27402-108">Ein Material wird angegeben, um auf der Oberfläche des Objekts (in diesem Beispiel ein linearer Farbverlauf) mit angezeigt werden die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="27402-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="27402-109">Eine helle wird erstellt, um auf das Objekt mit verwendet <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="27402-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27402-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27402-110">Example</span></span>  
 <span data-ttu-id="27402-111">Der folgende Code zeigt, wie zum Erstellen einer 3D-Szene in XAML.</span><span class="sxs-lookup"><span data-stu-id="27402-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="27402-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27402-112">Example</span></span>  
 <span data-ttu-id="27402-113">Der folgende Code zeigt, wie die gleiche 3D-Szene in prozeduralem Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27402-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="27402-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27402-114">See Also</span></span>  
 [<span data-ttu-id="27402-115">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="27402-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
