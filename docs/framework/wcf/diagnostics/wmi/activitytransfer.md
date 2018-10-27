---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034421"
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
