---
title: 1150 - CompensationState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5debccf664768b84a7b213cd012b484df8fe3ef8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1150|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt eine Statusänderung in einer CompensableActivity an.  
  
## <a name="message"></a>Meldung  
 CompensableActivity '%1' hat den Status '%2'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|Zustand|xs:string|Der Kompensationsstatus.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
