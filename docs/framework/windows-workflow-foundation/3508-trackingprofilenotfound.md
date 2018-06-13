---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512183"
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
