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
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113494"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget-Schnittstelle
Stellt Methoden für die Interaktion mit einem Ziel Element des Common Language Runtime (CLR) bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetCurrentThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.|  
|[GetImageBase-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Ruft die Basis Speicheradresse für das angegebene Bild ab.|  
|[GetMachineType-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Ruft einen Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.|  
|[GetPointerSize-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Ruft die Größe eines Zeigers auf das aktuelle Ziel in Bytes ab.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.|  
|[GetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Ruft einen Wert im lokalen Thread Speicher (TLS) am angegebenen Index für den angegebenen Thread ab.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Liest Daten aus der angegebenen Adresse des virtuellen Speichers in den angegebenen Puffer.|  
|[Request-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.|  
|[SetTLSValue-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.|  
|[WriteVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
