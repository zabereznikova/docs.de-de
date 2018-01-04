---
title: 440 - StartSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7772bcd8d637b14e3f91feceaccc9f045f390c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
