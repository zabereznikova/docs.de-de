---
title: 'Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4cc4b1a3e68d6d39e13a56b2a519d15b72bd3a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="41e12-102">Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches</span><span class="sxs-lookup"><span data-stu-id="41e12-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="41e12-103">Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="41e12-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="41e12-104">So zeigen Sie eine Liste der Assemblys im globalen Assemblycache an</span><span class="sxs-lookup"><span data-stu-id="41e12-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="41e12-105">Geben Sie an der [Visual Studio-Eingabeaufforderung](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="41e12-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="41e12-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="41e12-106">**gacutil -l** </span></span>  
     <span data-ttu-id="41e12-107">- oder - </span><span class="sxs-lookup"><span data-stu-id="41e12-107">-or-</span></span>  
    <span data-ttu-id="41e12-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="41e12-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="41e12-109">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) das Anzeigen des globalen Assemblycaches im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="41e12-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="41e12-110">Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="41e12-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e12-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41e12-111">See Also</span></span>  
 [<span data-ttu-id="41e12-112">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="41e12-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="41e12-113">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="41e12-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
