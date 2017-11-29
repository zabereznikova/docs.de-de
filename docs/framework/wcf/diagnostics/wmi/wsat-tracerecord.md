---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3966311bc10b5ad2ee401ef9e3e13c8f36e14505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Syntax  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Klasse WSAT_TraceRecord definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:  
  
### <a name="activityid"></a>ActivityID  
 Datentyp: object  
Zugriffstyp: Schreibgeschützt  
  
 Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.  
  
### <a name="eventid"></a>EventID  
 Datentyp: sint32  
Zugriffstyp: Schreibgeschützt  
  
 Die Ziel-ID des Ablaufverfolgungsdatensatzes.  
  
### <a name="tracerecord"></a>TraceRecord  
 Datentyp: string (Zeichenfolge)  
Zugriffstyp: Schreibgeschützt  
  
 TraceRecord  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
