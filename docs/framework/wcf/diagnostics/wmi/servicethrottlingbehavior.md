---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 9a7fbf93dbdbf1a6debcf865b4883b5784e2ff4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487606"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Syntax  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die ServiceThrottlingBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die ServiceThrottlingBehavior-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl an Nachrichten, die die Verteilerobjekte in einem ServiceHost aktiv verarbeiten.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl der Dienstobjekte, die gleichzeitig ausgeführt werden können.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl an Sitzungen, die ein Host gleichzeitig annehmen kann.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
