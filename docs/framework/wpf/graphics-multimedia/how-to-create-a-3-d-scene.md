---
title: 'Gewusst wie: Erstellen einer 3D-Szene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112101"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="e03c8-102">Gewusst wie: Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="e03c8-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="e03c8-103">In diesem Beispiel wird gezeigt, wie Sie ein 3D-Objekt erstellen, das wie ein flaches Blatt Papier aussieht, das gedreht wurde.</span><span class="sxs-lookup"><span data-stu-id="e03c8-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="e03c8-104">Zum <xref:System.Windows.Controls.Viewport3D> Erstellen dieser einfachen 3D-Szene werden a zusammen mit den folgenden Komponenten verwendet:</span><span class="sxs-lookup"><span data-stu-id="e03c8-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="e03c8-105">Eine Kamera wird <xref:System.Windows.Media.Media3D.PerspectiveCamera>mit einer erstellt.</span><span class="sxs-lookup"><span data-stu-id="e03c8-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="e03c8-106">Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e03c8-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="e03c8-107">Ein Netz wird erstellt, um die Form des 3D-Objekts (Blatt Papier) mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft von <xref:System.Windows.Media.Media3D.GeometryModel3D>anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e03c8-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="e03c8-108">Es wird ein Material angegeben, das auf der Oberfläche des Objekts (linearer Gradient in diesem Beispiel) mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft von <xref:System.Windows.Media.Media3D.GeometryModel3D>angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e03c8-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="e03c8-109">Es wird ein Licht erzeugt, <xref:System.Windows.Media.Media3D.DirectionalLight>das mit dem auf das Objekt scheint.</span><span class="sxs-lookup"><span data-stu-id="e03c8-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03c8-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e03c8-110">Example</span></span>  
 <span data-ttu-id="e03c8-111">Der folgende Code zeigt, wie Sie eine 3D-Szene in XAML erstellen.</span><span class="sxs-lookup"><span data-stu-id="e03c8-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e03c8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e03c8-112">Example</span></span>  
 <span data-ttu-id="e03c8-113">Der folgende Code zeigt, wie Sie dieselbe 3D-Szene im Verfahrenscode erstellen.</span><span class="sxs-lookup"><span data-stu-id="e03c8-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e03c8-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e03c8-114">See also</span></span>

- [<span data-ttu-id="e03c8-115">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="e03c8-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
