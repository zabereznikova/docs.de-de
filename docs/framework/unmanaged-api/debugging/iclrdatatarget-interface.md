---
title: ICLRDataTarget-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73966ffe89f0e84d5a516f20962472d900332faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget-Schnittstelle
Stellt Methoden für die Interaktion mit einem Zielelement der common Language Runtime (CLR) bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetCurrentThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Ruft den Bezeichner des Betriebssystems für den aktuellen Thread ab.|  
|[GetImageBase-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Ruft die Basis Speicheradresse für das angegebene Bild ab.|  
|[GetMachineType-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Ruft einen Bezeichner für die Art der Anweisungssatz, der der Zielprozess verwendet.|  
|[GetPointerSize-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Ruft die Größe in Bytes, der einen Zeiger auf das aktuelle Ziel an.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.|  
|[GetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Ruft einen Wert im lokalen Threadspeicher (TLS) am angegebenen Index für den angegebenen Thread ab.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.|  
|[Request-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Wird von der common Language Runtime (CLR) Daten Access Services zum Anfordern eines Vorgangs aufgerufen, wie durch die Implementierung definiert.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Legt den aktuellen Kontext des angegebenen Threads im Zielprozess.|  
|[SetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.|  
|[WriteVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Schreibt Daten aus dem angegebenen Puffer auf die angegebene virtuelle Speicheradresse.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle für die jeweiligen Zielelement geeigneten Form implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
