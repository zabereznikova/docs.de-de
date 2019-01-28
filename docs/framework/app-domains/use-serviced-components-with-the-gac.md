---
title: Verwenden von Serviced Components mit dem globalen Assemblycache
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d42fa296585d26186a2e75a49c5b3cf761e846
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583245"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a>Verwenden von Serviced Components mit dem globalen Assemblycache
Serviced Components (COM+-Komponenten mit verwaltetem Code) sollten im globalen Assemblycache abgelegt werden. Nur in bestimmten Szenarios können die Common Language Runtime und die COM+-Dienste mit Serviced Components umgehen, die sich nicht im globalen Assemblycache befinden. Folgende Beispielszenarien verdeutlichen dies:  
  
-   Für Serviced Components in einer COM+-Serveranwendung muss sich die Assembly, die die Komponenten enthält, im globalen Assemblycache befinden. Der Grund dafür ist, dass die Dllhost.exe-Datei nicht in dem Verzeichnis ausgeführt werden kann, das die Serviced Components enthält.  
  
-   Bei Serviced Components in einer COM+-Bibliotheksanwendung können die Common Language Runtime und die COM+-Dienste durch Durchsuchen des aktuellen Verzeichnisses den Verweis auf die Assembly auflösen. Demzufolge muss sich in diesem Fall die Assembly nicht unbedingt im globalen Assemblycache befinden.  
  
-   Bei Serviced Components in einer ASP.NET-Anwendung stellt sich die Situation anders dar. Wenn Sie die Assembly, die Serviced Components enthält, im Verzeichnis „bin“ des Anwendungsstamms ablegen und bedarfsabhängige Registrierung verwenden, wird die Assembly mittels Spiegelung in den Downloadcache kopiert, da ASP.NET die Spiegelungsfunktionen der Common Language Runtime verwendet.  
  
## <a name="see-also"></a>Siehe auch
- [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
