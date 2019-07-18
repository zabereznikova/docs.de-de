---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755596"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3503|  
|Schlüsselwörter|WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine doppelte CorrelationQuery gefunden wurde. Die doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## <a name="message"></a>Meldung  
 Es wurde eine doppelte CorrelationQuery mit Where='%1' gefunden. Diese doppelte Abfrage wird beim Berechnen von Korrelationen nicht verwendet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Where|xs:string|Where-Abschnitt der Korrelationsabfrage.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
