---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
