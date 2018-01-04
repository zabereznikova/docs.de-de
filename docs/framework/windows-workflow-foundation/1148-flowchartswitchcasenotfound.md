---
title: 1148 - FlowchartSwitchCaseNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0735351f0f5fb830b889d012fd91e3cc99eb255f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1148---flowchartswitchcasenotfound"></a>1148 - FlowchartSwitchCaseNotFound
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1148|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass bei einem Flussdiagrammwechsel weder ein übereinstimmender noch ein Standardfall gefunden wurden. Die Ausführung des Flussdiagramms wird beendet.  
  
## <a name="message"></a>Meldung  
 Flussdiagramm '%1'/FlowSwitch - Es wurde weder eine Case-Aktivität noch ein Standardfall gefunden, der dem Ergebnis des Ausdrucks entspricht. Die Ausführung des Flussdiagramms wird beendet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|Der Anzeigename des FlowChart.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
