---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274048"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung eines Diensts Verträge unterstützt.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung geordnete Nachrichten unterstützt.  
  
### <a name="targetcontract"></a>TargetContract  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vertrag, für den sie gilt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
