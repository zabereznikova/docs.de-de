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
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches
Verwenden Sie das [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a>So zeigen Sie eine Liste der Assemblys im globalen Assemblycache an  
  
1.  Geben Sie an der [Visual Studio-Eingabeaufforderung](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:  
  
     **gacutil -l**   
     - oder -   
    **gacutil /l**  
  
 In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung [Shfusion.dll](http://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) das Anzeigen des globalen Assemblycaches im Datei-Explorer. Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
