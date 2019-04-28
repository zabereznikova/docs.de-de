---
title: Verwenden der doppelten Pufferung
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777155"
---
# <a name="using-double-buffering"></a><span data-ttu-id="42f64-102">Verwenden der doppelten Pufferung</span><span class="sxs-lookup"><span data-stu-id="42f64-102">Using Double Buffering</span></span>
<span data-ttu-id="42f64-103">Sie können doppelt gepufferte Grafiken verwenden, um Flimmern in Ihren Anwendungen zu verringern, die komplexe Zeichenoperationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="42f64-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="42f64-104">Das .NET Framework enthält integrierten Unterstützung für die doppelte Pufferung oder können Sie verwalten und Rendern von Grafiken manuell.</span><span class="sxs-lookup"><span data-stu-id="42f64-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42f64-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="42f64-105">In This Section</span></span>  
 [<span data-ttu-id="42f64-106">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="42f64-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="42f64-107">Führt die doppelte Pufferung Konzept und stellt .NET Framework-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="42f64-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="42f64-108">Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="42f64-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="42f64-109">Veranschaulicht, wie die Unterstützung der doppelten Pufferung in .NET Framework verwendet.</span><span class="sxs-lookup"><span data-stu-id="42f64-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="42f64-110">Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="42f64-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="42f64-111">Zeigt, wie zum Verwalten der doppelten Pufferung in Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="42f64-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="42f64-112">Vorgehensweise: Manuelles Rendern von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="42f64-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="42f64-113">Doppelt gepufferte Grafiken zu rendern veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="42f64-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="42f64-114">Referenz</span><span class="sxs-lookup"><span data-stu-id="42f64-114">Reference</span></span>  
 <span data-ttu-id="42f64-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="42f64-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="42f64-116">Steuerelementmethode, die doppelte Pufferung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="42f64-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="42f64-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="42f64-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="42f64-118">Stellt Methoden zum Erstellen von Grafikpuffern bereit.</span><span class="sxs-lookup"><span data-stu-id="42f64-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="42f64-119">Bietet Zugriff auf den Kontext von gepufferten Grafiken für eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="42f64-119">Provides access to the buffered graphics context for a application domain.</span></span>
