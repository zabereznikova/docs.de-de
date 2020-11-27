---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: cb99fd72165182788955021fbedd2aa657b3a098
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275322"
---
# <a name="1023---completebookmarkworkitem"></a>1023 - CompleteBookmarkWorkItem

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|1023|  
|Keywords|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass ein BookmarkWorkItem abgeschlossen wurde.  
  
## <a name="message"></a>`Message`  

 Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein BookmarkWorkItem abgeschlossen. BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|BookmarkName|xs:string|Der Name des Lesezeichens.|  
|BookmarkScope|xs:string|Der Bereich des Lesezeichens.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
