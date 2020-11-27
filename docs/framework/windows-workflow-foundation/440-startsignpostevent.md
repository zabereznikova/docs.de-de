---
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 1e0278d665a961afab21445ab8490e3e5a94987c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293454"
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent1

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|440|  
|Keywords|Problembehandlung|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt in der Aktivitätsablaufverfolgung eine Nachricht an, die das Überschreiten einer Aktivitätsgrenze beim Senden oder Empfangen gestartet hat.  
  
## <a name="message"></a>`Message`  

 Aktivitätsgrenze.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|Der Name der Aktivität.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
