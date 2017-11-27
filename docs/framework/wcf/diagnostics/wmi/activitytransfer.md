---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a>ActivityTransfer
Aktivitätsübertragungsereignis  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
### <a name="activityid"></a>ActivityID  
  
-   Datentyp: object  
    Zugriffstyp: Schreibgeschützt  
  
-   Aktivitäts-ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   Datentyp: object  
    Zugriffstyp: Schreibgeschützt  
  
-   Verwandte Aktivitäts-ID  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
