---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261162"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 - MaxPendingMessagesPerChannelExceeded

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|3552|  
|Keywords|Kontingent, WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.  
  
## <a name="message"></a>`Message`  

 Die Drosselungsgrenze 'MaxPendingMessagesPerChannel' von '%1' wurde erreicht. Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Begrenzung|xs:string|Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
