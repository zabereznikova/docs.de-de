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
ms.openlocfilehash: 0d3e6a95d8fd71a67b97923dac53c1f615dfe666
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703420"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget-Schnittstelle

Stellt Methoden für die Interaktion mit einem Ziel Element des Common Language Runtime (CLR) bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetCurrentThreadID-Methode](iclrdatatarget-getcurrentthreadid-method.md)|Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.|  
|[GetImageBase-Methode](iclrdatatarget-getimagebase-method.md)|Ruft die Basis Speicheradresse für das angegebene Bild ab.|  
|[GetMachineType-Methode](iclrdatatarget-getmachinetype-method.md)|Ruft einen Bezeichner für die Art von Anweisungs Satz ab, die vom Ziel Prozess verwendet wird.|  
|[GetPointerSize-Methode](iclrdatatarget-getpointersize-method.md)|Ruft die Größe eines Zeigers auf das aktuelle Ziel in Bytes ab.|  
|[GetThreadContext-Methode](iclrdatatarget-getthreadcontext-method.md)|Ruft einen Zeiger auf den Kontext des Threads mit dem angegebenen Bezeichner ab.|  
|[GetTLSValue-Methode](iclrdatatarget-gettlsvalue-method.md)|Ruft einen Wert im lokalen Thread Speicher (TLS) am angegebenen Index für den angegebenen Thread ab.|  
|[ReadVirtual-Methode](iclrdatatarget-readvirtual-method.md)|Liest Daten aus der angegebenen Adresse des virtuellen Speichers in den angegebenen Puffer.|  
|[Request Method](iclrdatatarget-request-method.md)|Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.|  
|[SetThreadContext-Methode](iclrdatatarget-setthreadcontext-method.md)|Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.|  
|[SetTLSValue-Methode](iclrdatatarget-settlsvalue-method.md)|Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.|  
|[WriteVirtual-Methode](iclrdatatarget-writevirtual-method.md)|Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.|  
  
## <a name="remarks"></a>Hinweise  

 Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
