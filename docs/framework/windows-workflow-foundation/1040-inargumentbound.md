---
title: 1040 - InArgumentBound
ms.date: 03/30/2017
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
ms.openlocfilehash: 984372c07ccfb11f2f05d5488fa5ffc95075db41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009746"
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1040|  
|Schlüsselwörter|WFActivities|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, das ein In-Argument gebunden wurde.  
  
## <a name="message"></a>Meldung  
 Das Argument '%1' der Aktivität '%2', DisplayName: '%3', InstanceId: '%4' wurde mit Wert %5 gebunden.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|Der Name des InArgument.|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|Wert|xs:string|Der an das InArgument gebundene Wert.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
