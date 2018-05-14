---
title: Assemblyspeicherort
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91fc7cf6ea66952fa5770ce73ecb1a8c129a9a2d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-location"></a>Assemblyspeicherort
Der Speicherort einer Assembly bestimmt, ob die Common Language Runtime diese finden kann, wenn auf sie verwiesen wird. Ebenso bestimmt er, ob die Assembly für andere Assemblys freigegeben werden kann. Sie können eine Assembly in den folgenden Speicherorten bereitstellen:  
  
-   Die Verzeichnisse und Unterverzeichnisse der Anwendung  
  
     Dies ist der häufigste Speicherort für das Bereitstellen einer Assembly. Das Unterverzeichnis des Stammverzeichnisses einer Anwendung kann auf der Sprache oder der Kultur basieren. Wenn eine Assembly über Informationen im Kulturattribut verfügt, muss sie sich in einem Unterverzeichnis im Anwendungsverzeichnis mit dem Kulturnamen befinden.  
  
-   Im globalen Assemblycache.  
  
     Dabei handelt es sich um einen computerweiten Codecache, der überall dort installiert wird, wo auch die Common Language Runtime installiert ist. Wenn Sie eine Assembly für mehrere Anwendungen freigeben möchten, sollten Sie die Assembly in den meisten Fällen im globalen Assemblycache bereitstellen.  
  
-   Auf einem HTTP-Server  
  
     Eine auf einem HTTP-Server bereitgestellte Assembly muss einen starken Namen haben. Sie zeigen im Codebasisabschnitt Ihrer Anwendungskonfigurationsdatei auf die Assembly.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
