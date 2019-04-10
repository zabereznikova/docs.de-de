---
title: 'Vorgehensweise: Bestimmen der installierten Version von WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305675"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="edd7e-102">Vorgehensweise: Bestimmen der installierten Version von WPF</span><span class="sxs-lookup"><span data-stu-id="edd7e-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="edd7e-103">Die Versionsnummer für die derzeit installierte Version von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] befindet sich in der **Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="edd7e-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="edd7e-104">Um die Versionsnummer zu finden:</span><span class="sxs-lookup"><span data-stu-id="edd7e-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="edd7e-105">Auf der **starten** Menü klicken Sie auf **ausführen**.</span><span class="sxs-lookup"><span data-stu-id="edd7e-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="edd7e-106">In **öffnen**, Typ **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="edd7e-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="edd7e-107">Öffnen Sie den folgenden Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="edd7e-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="edd7e-108">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Versionsnummer befindet sich in der **Version** Wert.</span><span class="sxs-lookup"><span data-stu-id="edd7e-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
