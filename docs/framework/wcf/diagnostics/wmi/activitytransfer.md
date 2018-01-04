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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f3db50a32fabc117c79eef5ac086a7798f86ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
