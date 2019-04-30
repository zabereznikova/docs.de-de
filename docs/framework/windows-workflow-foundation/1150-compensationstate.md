---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923863"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1150|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt eine Statusänderung in einer CompensableActivity an.  
  
## <a name="message"></a>Meldung  
 CompensableActivity '%1' hat den Status '%2'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|Zustand|xs:string|Der Kompensationsstatus.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
