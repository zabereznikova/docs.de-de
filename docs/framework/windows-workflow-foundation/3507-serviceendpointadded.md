---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f06e6cccd9c4ca2907b86372f609f8c72b5e189
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3507|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein Dienstendpunkt hinzugefügt wurde.  
  
## <a name="message"></a>Meldung  
 Für Adresse '%1', Bindung '%2' und Vertrag '%3' wurde ein Dienstendpunkt hinzugefügt.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Adresse|xs:string|Die Adresse des Endpunkts.|  
|Bindung|xs:string|Die Bindung des Endpunkts.|  
|Vertrag|xs:string|Der Vertrag des Endpunkts.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
