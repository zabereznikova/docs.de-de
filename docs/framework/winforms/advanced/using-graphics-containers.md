---
title: Verwenden von Grafikcontainern
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525020"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="95480-102">Verwenden von Grafikcontainern</span><span class="sxs-lookup"><span data-stu-id="95480-102">Using Graphics Containers</span></span>
<span data-ttu-id="95480-103">Ein <xref:System.Drawing.Graphics> -Objekt stellt Methoden bereit, z. B. <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, und <xref:System.Drawing.Graphics.DrawString%2A> zum Anzeigen von Vektorgrafiken, Rasterbilder und Text.</span><span class="sxs-lookup"><span data-stu-id="95480-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="95480-104">Ein <xref:System.Drawing.Graphics> -Objekt verfügt außerdem über verschiedene Eigenschaften, die beeinflussen, die Qualität und die Ausrichtung der Elemente, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="95480-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="95480-105">So bestimmt beispielsweise die Glättungsmodus Mode-Eigenschaft, ob Antialiasing bei Linien und Kurven angewendet wird, und die World Transformationseigenschaft wirkt sich auf die Position und Drehung der Elemente, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="95480-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="95480-106">Ein <xref:System.Drawing.Graphics> Objekt jeweiligen Ausgabegeräts zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="95480-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="95480-107">Bei Verwendung einer <xref:System.Drawing.Graphics> Objekt, das in einem Fenster Zeichnen der <xref:System.Drawing.Graphics> Objekt wird auch mit dem jeweiligen Fenster zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="95480-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="95480-108">Ein <xref:System.Drawing.Graphics> Objekt kann betrachtet werden als Container, da es eine Reihe von Eigenschaften enthält, die Zeichnung auswirken und mit gerätespezifischen Informationen verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="95480-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="95480-109">Sie können einen sekundären Container in einem vorhandenen erstellen <xref:System.Drawing.Graphics> Objekt durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> -Methode dieses <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="95480-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95480-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="95480-110">In This Section</span></span>  
 [<span data-ttu-id="95480-111">Verwalten des Zustands eines Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="95480-111">Managing the State of a Graphics Object</span></span>](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="95480-112">Beschreibt, wie die Qualität, Clippingbereichs und Transformationen von Verwalten einer <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="95480-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="95480-113">Verwenden geschachtelter Grafikcontainer</span><span class="sxs-lookup"><span data-stu-id="95480-113">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 <span data-ttu-id="95480-114">Zeigt, wie Container verwenden, um den Zustand steuern die <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="95480-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
