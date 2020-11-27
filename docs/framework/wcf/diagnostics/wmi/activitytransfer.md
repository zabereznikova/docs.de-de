---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291114"
---
# <a name="activitytransfer"></a>ActivityTransfer

Aktivitätsübertragungsereignis  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Von der ActivityTransfer-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  

 Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:  
  
### <a name="activityid"></a>Aktivitäts-ID  
  
- Datentyp: object  
    Zugriffstyp: Schreibgeschützt  
  
- Aktivitäts-ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Datentyp: object  
    Zugriffstyp: Schreibgeschützt  
  
- Verwandte Aktivitäts-ID  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
