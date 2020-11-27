---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270327"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|3503|  
|Keywords|WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine doppelte CorrelationQuery gefunden wurde. Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## <a name="message"></a>`Message`  

 Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden. Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Hierbei gilt:|xs:string|Where-Abschnitt der Korrelationsabfrage.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
