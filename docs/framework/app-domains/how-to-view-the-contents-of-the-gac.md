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
ms.openlocfilehash: 3650de934cb3d2940d0e8e971d03aff856bddfd7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43394464"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches
Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a>So zeigen Sie eine Liste der Assemblys im globalen Assemblycache an  
  
1.  Geben Sie an der [Visual Studio-Eingabeaufforderung](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:  
  
     **gacutil -l**   
     - oder -   
    **gacutil /l**  
  
 In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) das Anzeigen des globalen Assemblycaches im Datei-Explorer. Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
