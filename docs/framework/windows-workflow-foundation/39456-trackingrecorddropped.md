---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de056ffcdfeb3ea5dee9eaca213fe96ee991d067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="39456---trackingrecorddropped"></a>39456 - TrackingRecordDropped
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|39456|  
|Schlüsselwörter|WFTracking|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein Nachverfolgungsdatensatz gelöscht wurde, weil sein Größe den maximal zulässigen Wert des ETW-Sitzungsanbieters überschreitet.  
  
## <a name="message"></a>Meldung  
 Die Größe des Überwachungsdatensatzes %1 überschreitet das zulässige Maximum der ETW-Sitzung für den Anbieter %2.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Ausnahme|xs:string|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
