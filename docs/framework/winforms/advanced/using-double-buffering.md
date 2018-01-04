---
title: Verwenden der doppelten Pufferung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a><span data-ttu-id="58e9f-102">Verwenden der doppelten Pufferung</span><span class="sxs-lookup"><span data-stu-id="58e9f-102">Using Double Buffering</span></span>
<span data-ttu-id="58e9f-103">Sie können doppelt gepufferte Grafiken verwenden, um Flackern in Ihren Anwendungen zu reduzieren, die komplexe Zeichenoperationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="58e9f-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="58e9f-104">.NET Framework enthält integrierte Unterstützung für die doppelte Pufferung, oder Sie verwalten und Rendern von Grafiken manuell.</span><span class="sxs-lookup"><span data-stu-id="58e9f-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58e9f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="58e9f-105">In This Section</span></span>  
 [<span data-ttu-id="58e9f-106">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="58e9f-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="58e9f-107">Führt die doppelte Pufferung und erläutert .NET Framework-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="58e9f-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="58e9f-108">Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="58e9f-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="58e9f-109">Veranschaulicht, wie die standardmäßige Unterstützung der doppelten Pufferung in .NET Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="58e9f-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="58e9f-110">Gewusst wie: Manuelles Verwalten von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="58e9f-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="58e9f-111">Zeigt, wie der doppelten Pufferung in Anwendungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="58e9f-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="58e9f-112">Gewusst wie: Manuelles Rendern von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="58e9f-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="58e9f-113">Doppelt gepufferte Grafiken rendern veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58e9f-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="58e9f-114">Verweis</span><span class="sxs-lookup"><span data-stu-id="58e9f-114">Reference</span></span>  
 <span data-ttu-id="58e9f-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="58e9f-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="58e9f-116">Steuerelementmethode, die doppelte Pufferung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="58e9f-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="58e9f-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="58e9f-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="58e9f-118">Stellt Methoden zum Erstellen von Grafikpuffern bereit.</span><span class="sxs-lookup"><span data-stu-id="58e9f-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="58e9f-119">Bietet Zugriff auf den Kontext von gepufferten Grafiken für eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="58e9f-119">Provides access to the buffered graphics context for a application domain.</span></span>
