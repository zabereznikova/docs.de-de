---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774412"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|39458|  
|Schlüsselwörter|WFTracking|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein Nachverfolgungsdatensatz abgeschnitten wurde. Variablen, Anmerkungen und Benutzerdaten wurden entfernt.  
  
## <a name="message"></a>Meldung  
 Abgeschnittener Überwachungsdatensatz %1 wurde in die ETW-Sitzung mit Anbieter %2 geschrieben. Variablen, Anmerkungen und Benutzerdaten wurden entfernt.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Die Nummer des Nachverfolgungsdatensatzes.|  
|ProviderId|xs:string|Die ETW-Anbieter-ID.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
