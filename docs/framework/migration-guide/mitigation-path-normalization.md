---
title: "Entschärfung: Pfadnormalisierung"
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
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e30099e315f88bd051dca2e1f6c83d1bccc49569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-path-normalization"></a>Entschärfung: Pfadnormalisierung
Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Pfadnormalisierung in .NET Framework geändert.  
  
## <a name="what-is-path-normalization"></a>Was ist Pfadnormalisierung?  
 Das Normalisieren eines Pfads beinhaltet das Verändern der Zeichenfolge, die einen Pfad oder eine Datei kennzeichnet, in einer Weise, dass sie einem gültigen Pfad im Zielbetriebssystem entspricht. Normalisierung umfasst ist in der Regel:  
  
-   Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.  
  
-   Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.  
  
-   Die Auswertung des relativen Verzeichnisses (`.`) oder des übergeordneten Verzeichnisses (`..`) in einem Pfad.  
  
-   Das Verkürzen um angegebene Zeichen.  
  
## <a name="the-changes"></a>Die Änderungen  
 Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Pfadnormalisierung in folgender Weise geändert:  
  
-   Die Runtime greift auf die Funktion [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) des Betriebssystems zurück, um Pfade zu normalisieren.  
  
-   Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).  
  
-   Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.  
  
-   Die Runtime überprüft Gerätesyntaxpfade nicht.  
  
-   Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.  
  
## <a name="impact"></a>Auswirkungen  
 Für Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher sind diese Änderungen standardmäßig aktiviert. Sie sollten die Leistung verbessern und Methoden zugleich den Zugriff auf zuvor nicht zugängliche Pfade ermöglichen.  
  
 Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.  
  
## <a name="mitigation"></a>Problemumgehung  
 Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher können sich gegen diese Änderung entscheiden und Legacynormalisierung verwenden, indem dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei Folgendes hinzugefügt wird:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder früher, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung verwenden, indem dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
