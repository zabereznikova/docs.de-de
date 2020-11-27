---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271238"
---
# <a name="2577---trycatchexceptionduringcancelation"></a>2577 - TryCatchExceptionDuringCancelation

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|2577|  
|Keywords|WFActivities|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine untergeordnete Aktivität der TryCatch-Aktivität während des Abbruchs eine Ausnahme ausgelöst hat.  
  
## <a name="message"></a>`Message`  

 Eine untergeordnete Aktivität der TryCatch-Aktivität '%1' hat während des Abbruchs eine Ausnahme ausgelöst.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
