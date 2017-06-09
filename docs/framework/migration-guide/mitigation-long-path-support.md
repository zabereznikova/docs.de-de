---
title: "Entschärfung: Unterstützung für lange Pfade | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 40b4b94ac3058dda88b44c82110d4c749566e2b2
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-long-path-support"></a>Entschärfung: Unterstützung für lange Pfade
Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an lösen E/A-Methoden des Dateisystems nicht mehr automatisch eine <xref:System.IO.PathTooLongException> aus, wenn ein Pfad oder ein vollqualifizierter Dateiname 260 (oder `MAX_PATH`) Zeichen überschreitet. Stattdessen werden lange Pfade mit bis zu 32.000 Zeichen unterstützt.  
  
## <a name="impact"></a>Auswirkungen  
 Für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] neu kompilierte Anwendungen, die zuvor automatisch eine <xref:System.IO.PathTooLongException>-Ausnahme auslösten, wenn ein Pfad die Länge von 260 Zeichen überschritt, lösen jetzt nur unter den folgenden Bedingungen eine <xref:System.IO.PathTooLongException> aus:  
  
-   Die Länge des Pfads umfasst mehr als <xref:System.Int16.MaxValue?displayProperty=fullName> (32.767) Zeichen.  
  
-   Das Betriebssystem gibt `COR_E_PATHTOOLONG` oder einen dazu äquivalenten Wert zurück.  
  
 Das Legacyverhalten für Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früher ist, dass die Runtime automatisch eine <xref:System.IO.PathTooLongException> auslöst, wenn ein Pfad die Länge von 260 Zeichen überschreitet.  
  
## <a name="mitigation"></a>Problemumgehung  
 Für Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] können Sie sich gegen die Unterstützung von langen Pfaden entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer app.config-Datei hinzufügen:  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, erlauben die Entscheidung für die Unterstützung von langen Pfaden, indem Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der app.config-Datei hinzugefügt wird:  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

