---
title: 'Vorgehensweise: Erstellen einer 3D-Szene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8e176cb437055787da86d56770dd71323134fa33
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126229"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="46aa0-102">Vorgehensweise: Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="46aa0-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="46aa0-103">Dieses Beispiel zeigt, wie Sie ein 3D-Objekt erstellen, der einem flachen Blatt Papier ähnelt dem gedreht wurde.</span><span class="sxs-lookup"><span data-stu-id="46aa0-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="46aa0-104">Ein <xref:System.Windows.Controls.Viewport3D> zusammen mit den folgenden Komponenten verwendet, um diese einfache 3D-Szene zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="46aa0-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="46aa0-105">Eine Kamera wurde mit einem <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="46aa0-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="46aa0-106">Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="46aa0-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="46aa0-107">Ein Mesh erstellt, um die Form eines 3D-Objekts (Blatt Papier) mit anzugeben der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="46aa0-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="46aa0-108">Ein Material wird angegeben, um auf die Oberfläche des Objekts (in diesem Beispiel ein linearer Farbverlauf) mit angezeigt werden die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="46aa0-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="46aa0-109">Ein Licht wird erstellt, um auf das Objekt mit glänzen <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="46aa0-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46aa0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46aa0-110">Example</span></span>  
 <span data-ttu-id="46aa0-111">Der folgende Code zeigt, wie Sie eine 3D-Szene in XAML zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="46aa0-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="46aa0-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46aa0-112">Example</span></span>  
 <span data-ttu-id="46aa0-113">Der folgende Code zeigt, wie Sie die gleiche 3D-Szene in prozeduralem Code erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="46aa0-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="46aa0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46aa0-114">See also</span></span>

- [<span data-ttu-id="46aa0-115">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="46aa0-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
