---
title: ICLRDataTarget-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100248"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget-Schnittstelle
Stellt Methoden für die Interaktion mit der common Language Runtime (CLR) ein Target-Element.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetCurrentThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Ruft den Bezeichner für den aktuellen Thread ab.|  
|[GetImageBase-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Ruft die Basis Speicheradresse für das angegebene Bild ab.|  
|[GetMachineType-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Ruft einen Bezeichner für die Art der Anweisungssatz, der der Zielprozess verwendet.|  
|[GetPointerSize-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Ruft die Größe in Bytes, der einen Zeiger auf das aktuelle Ziel.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.|  
|[GetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Ruft einen Wert im lokalen Threadspeicher (TLS) am angegebenen Index für den angegebenen Thread an.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Liest Daten aus der angegebenen virtuellen Speicheradresse in den angegebenen Puffer.|  
|[Request-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Aufgerufen von der common Language Runtime (CLR) Datenzugriffsdiensten der zum Anfordern eines Vorgangs, wie durch die Implementierung definiert.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest.|  
|[SetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.|  
|[WriteVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Schreibt Daten aus dem angegebenen Puffer an die Adresse des angegebenen virtuellen Speicher an.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger), muss diese Schnittstelle für das betreffende Zielframework-Element entsprechend implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
