---
title: 'Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches'
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6e582f86eac03a51437b965f87f1bc7f29294eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743705"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="aaa8f-102">Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches</span><span class="sxs-lookup"><span data-stu-id="aaa8f-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="aaa8f-103">Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aaa8f-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="aaa8f-104">So zeigen Sie eine Liste der Assemblys im globalen Assemblycache an</span><span class="sxs-lookup"><span data-stu-id="aaa8f-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="aaa8f-105">Geben Sie an der [Visual Studio-Eingabeaufforderung](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="aaa8f-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="aaa8f-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="aaa8f-106">**gacutil -l** </span></span>  
     <span data-ttu-id="aaa8f-107">- oder - </span><span class="sxs-lookup"><span data-stu-id="aaa8f-107">-or-</span></span>  
    <span data-ttu-id="aaa8f-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="aaa8f-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="aaa8f-109">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) das Anzeigen des globalen Assemblycaches im Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="aaa8f-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="aaa8f-110">Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="aaa8f-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa8f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaa8f-111">See Also</span></span>  
 [<span data-ttu-id="aaa8f-112">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="aaa8f-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="aaa8f-113">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="aaa8f-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
