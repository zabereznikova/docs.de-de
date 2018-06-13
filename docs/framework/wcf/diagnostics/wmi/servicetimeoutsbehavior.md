---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 7531cf27aec0ea9a71ee7b1906e8f7cee151695f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485953"
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior
ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Syntax  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die ServiceTimeoutsBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die ServiceTimeoutsBehavior-Klasse verfügt über die folgende Eigenschaft:  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
