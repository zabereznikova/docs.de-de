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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
