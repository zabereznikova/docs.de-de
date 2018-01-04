---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e297bfc0499ea3ee8d3dd8395165ca22b2baa1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Syntax  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung eines Diensts Verträge unterstützt.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung geordnete Nachrichten unterstützt.  
  
### <a name="targetcontract"></a>TargetContract  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vertrag, für den sie gilt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
