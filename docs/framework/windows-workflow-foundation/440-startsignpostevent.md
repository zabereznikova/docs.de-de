---
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 4b2b6b0fa9df4725edd4929512eb1d7534d933b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774136"
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent1
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|440|  
|Schlüsselwörter|Problembehandlung|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt in der Aktivitätsablaufverfolgung eine Nachricht an, die das Überschreiten einer Aktivitätsgrenze beim Senden oder Empfangen gestartet hat.  
  
## <a name="message"></a>Meldung  
 Aktivitätsgrenze.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|Der Name der Aktivität.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
