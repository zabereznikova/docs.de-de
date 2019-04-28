---
title: Verwenden von Grafikcontainern
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766154"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="665d9-102">Verwenden von Grafikcontainern</span><span class="sxs-lookup"><span data-stu-id="665d9-102">Using Graphics Containers</span></span>
<span data-ttu-id="665d9-103">Ein <xref:System.Drawing.Graphics> Objekt bietet Methoden, wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, und <xref:System.Drawing.Graphics.DrawString%2A> für die Anzeige von Vektorgrafiken, Rasterbilder und Text.</span><span class="sxs-lookup"><span data-stu-id="665d9-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="665d9-104">Ein <xref:System.Drawing.Graphics> Objekt verfügt auch über mehrere Eigenschaften, die beeinflussen, die Qualität und die Ausrichtung der Elemente, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="665d9-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="665d9-105">Beispielsweise bestimmt die Glättung Mode-Eigenschaft an, ob Antialiasing auf Linien und Kurven angewendet wird, und die Welt Transformationseigenschaft wirkt sich auf die Position und Drehung der Elemente, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="665d9-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="665d9-106">Ein <xref:System.Drawing.Graphics> Objekt jeweiligen Ausgabegeräts zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="665d9-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="665d9-107">Bei Verwendung einer <xref:System.Drawing.Graphics> Objekt, das in einem Fenster, zeichnen die <xref:System.Drawing.Graphics> -Objekt bezieht sich auch mit dem jeweiligen Fenster.</span><span class="sxs-lookup"><span data-stu-id="665d9-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="665d9-108">Ein <xref:System.Drawing.Graphics> Objekt kann betrachtet werden als Container, da sie einen Satz von Eigenschaften enthält, die Zeichnung zu beeinflussen, und klicken Sie mit gerätespezifischen Informationen verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="665d9-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="665d9-109">Sie können einen sekundären Container in einem vorhandenen erstellen <xref:System.Drawing.Graphics> -Objekt durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> -Methode dieses <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="665d9-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="665d9-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665d9-110">In This Section</span></span>  
 [<span data-ttu-id="665d9-111">Verwalten des Zustands eines Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="665d9-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="665d9-112">Beschreibt, wie verwalten Sie Einstellungen von Quality, Clippingbereichs und Transformationen von einem <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="665d9-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="665d9-113">Verwenden geschachtelter Grafikcontainer</span><span class="sxs-lookup"><span data-stu-id="665d9-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="665d9-114">Zeigt, wie Sie Container verwenden, um die Steuerung des Status des der <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="665d9-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
