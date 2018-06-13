---
title: 1148 - FlowchartSwitchCaseNotFound
ms.date: 03/30/2017
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
ms.openlocfilehash: 7e96b5b7652d404e6fdbe2c04c6a4069ca78f20f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511958"
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
