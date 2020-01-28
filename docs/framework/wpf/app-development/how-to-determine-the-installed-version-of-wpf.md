---
title: Ermitteln der installierten Version von WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735697"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="ba7a8-102">Gewusst wie: Bestimmen der installierten WPF-Version</span><span class="sxs-lookup"><span data-stu-id="ba7a8-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="ba7a8-103">Die Versionsnummer für die aktuell installierte Version von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] befindet sich in der **Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="ba7a8-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="ba7a8-104">So finden Sie die Versionsnummer:</span><span class="sxs-lookup"><span data-stu-id="ba7a8-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="ba7a8-105">Klicken Sie im **Startmenü** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba7a8-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="ba7a8-106">Geben Sie in **Öffnen**den Befehl **Regedit. exe**ein.</span><span class="sxs-lookup"><span data-stu-id="ba7a8-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="ba7a8-107">Öffnen Sie den folgenden Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="ba7a8-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="ba7a8-108">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Versionsnummer wird im **Versions** Wert gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ba7a8-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
