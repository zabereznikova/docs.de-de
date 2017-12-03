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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
