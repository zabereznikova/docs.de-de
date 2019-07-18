---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925189"
---
# <a name="1013---completeexecuteactivityworkitem"></a>1013 - CompleteExecuteActivityWorkItem
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1013|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein ExecuteActivityWorkItem abgeschlossen wurde.  
  
## <a name="message"></a>Meldung  
 Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine ExecuteActivityWorkItem abgeschlossen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
