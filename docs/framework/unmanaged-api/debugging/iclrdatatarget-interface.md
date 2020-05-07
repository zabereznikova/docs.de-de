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
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860565"
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
|[Anforderungs Methode](iclrdatatarget-request-method.md)|Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.|  
|[SetThreadContext-Methode](iclrdatatarget-setthreadcontext-method.md)|Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest.|  
|[SetTLSValue-Methode](iclrdatatarget-settlsvalue-method.md)|Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.|  
|[WriteVirtual-Methode](iclrdatatarget-writevirtual-method.md)|Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle entsprechend für das jeweilige Ziel Element implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
