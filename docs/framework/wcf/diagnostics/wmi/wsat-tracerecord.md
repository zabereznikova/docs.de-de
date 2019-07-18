---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923408"
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
