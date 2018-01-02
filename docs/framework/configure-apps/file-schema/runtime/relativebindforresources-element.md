---
title: '&lt;RelativeBindForResources&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8409b1fe86776397ceb3db5b338fb8aaadef9cbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltrelativebindforresourcesgt-element"></a>&lt;RelativeBindForResources&gt; Element
Optimiert den Test für Satellitenassemblys.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<RelativeBindForResources >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die common Language Runtime die Überprüfung von Satellitenassemblys optimiert.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Common Language Runtime wird die Überprüfung für Satellitenassemblys nicht optimiert werden. Dies ist der Standardwert.|  
|`true`|Die Common Language Runtime optimiert die Überprüfung Satellitenassemblys.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen Ressourcen-Manager-Prüfpunkte für Ressourcen, wie beschrieben in der [Verpacken und Bereitstellen von Ressourcen](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) Thema. Dies bedeutet, dass beim Ressourcen-Manager für eine bestimmte lokalisierte Version einer Ressource Prüfpunkte, kann es suchen Sie im globalen Assemblycache, Satellitenassemblys in eine kulturspezifische Ordner in der Anwendung Code, Basisabfrage erstellt Windows Installer gesucht und Auslösen der <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis. Die `<relativeBindForResources>` Element optimiert die Möglichkeit, in dem Ressourcen-Manager-für Satellitenassemblys Prüfpunkte. Sie können die Leistung verbessern, bei der Suche nach Ressourcen in den folgenden Situationen:  
  
-   Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird. Das heißt, wenn die Codeassembly im globalen Assemblycache installiert ist, müssen die Satellitenassemblys auch es installiert sein. Wenn die Codeassembly in die Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner, in die CodeBase installiert.  
  
-   Wenn Windows Installer wird nicht verwendet oder nur selten verwendet für die Installation von Satellitenassemblys bei Bedarf.  
  
-   Wenn Anwendungscode behandelt nicht das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis.  
  
 Festlegen der `enabled` Attribut des der `<relativeBindForResources>` Element `true` optimiert Ressourcen-Manager-Test für Satellitenassemblys wie folgt:  
  
-   Den Speicherort der übergeordneten Codeassembly verwendet, um für die Suche nach der Satellitenassembly.  
  
-   Windows Installer ist nicht für Satellitenassemblys abgefragt werden.  
  
-   Es wird nicht ausgelöst. die <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis.  
  
## <a name="see-also"></a>Siehe auch  
 [Verpacken und Bereitstellen von Ressourcen](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
