---
title: Assemblyspeicherort
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c736b4fe2a4bc38d4345413fa00d4cf7e5a80be7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607745"
---
# <a name="assembly-location"></a>Assemblyspeicherort
Der Speicherort einer Assembly bestimmt, ob die Common Language Runtime diese finden kann, wenn auf sie verwiesen wird. Ebenso bestimmt er, ob die Assembly für andere Assemblys freigegeben werden kann. Sie können eine Assembly in den folgenden Speicherorten bereitstellen:  
  
- Die Verzeichnisse und Unterverzeichnisse der Anwendung  
  
     Dies ist der häufigste Speicherort für das Bereitstellen einer Assembly. Das Unterverzeichnis des Stammverzeichnisses einer Anwendung kann auf der Sprache oder der Kultur basieren. Wenn eine Assembly über Informationen im Kulturattribut verfügt, muss sie sich in einem Unterverzeichnis im Anwendungsverzeichnis mit dem Kulturnamen befinden.  
  
- Im globalen Assemblycache.  
  
     Dabei handelt es sich um einen computerweiten Codecache, der überall dort installiert wird, wo auch die Common Language Runtime installiert ist. Wenn Sie eine Assembly für mehrere Anwendungen freigeben möchten, sollten Sie die Assembly in den meisten Fällen im globalen Assemblycache bereitstellen.  
  
- Auf einem HTTP-Server  
  
     Eine auf einem HTTP-Server bereitgestellte Assembly muss einen starken Namen haben. Sie zeigen im Codebasisabschnitt Ihrer Anwendungskonfigurationsdatei auf die Assembly.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)
- [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)
- [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
