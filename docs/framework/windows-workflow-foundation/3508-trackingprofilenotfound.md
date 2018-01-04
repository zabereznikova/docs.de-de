---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34812b6ddefb69c053cfefa91d7227a7bf15f42e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3508|  
|Schlüsselwörter|WFServices|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass entweder das TrackingProfile nicht in der Konfigurationsdatei gefunden wurde oder die ActivityDefinitionId nicht übereinstimmt.  
  
## <a name="message"></a>Meldung  
 TrackingProfile '%1' für die ActivityDefinitionId '%2' wurde nicht gefunden. Entweder wurde das TrackingProfile nicht in der Konfigurationsdatei gefunden, oder die ActivityDefinitionId stimmt nicht überein.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|Der Name des Nachverfolgungsprofils.|  
|ActivityDefinitionId|xs:string|Die Aktivitätsdefinitions-ID.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
