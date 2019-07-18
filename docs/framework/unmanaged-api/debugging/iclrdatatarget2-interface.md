---
title: ICLRDataTarget2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697939"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2-Schnittstelle
Eine Unterklasse von [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , die von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AllocVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|Belegt Speicher im Adressraum des Zielprozesses.|  
|[FreeVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|Gibt den Arbeitsspeicher, der zuvor im Adressbereich des Zielprozesses belegt wurde frei.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild. Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
