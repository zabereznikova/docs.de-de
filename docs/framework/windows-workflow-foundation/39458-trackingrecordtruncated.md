---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
