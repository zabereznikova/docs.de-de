---
title: ICLRDataTarget3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: af944a9c2bb04f37b06f27cfbe38e23c9613d768
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860414"
---
# <a name="iclrdatatarget3-interface"></a>ICLRDataTarget3-Schnittstelle
Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetExceptionRecord-Methode](iclrdatatarget3-getexceptionrecord-method.md)|Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.|  
|[GetExceptionContextRecord-Methode](iclrdatatarget3-getexceptioncontextrecord-method.md)|Wird durch die CLR-Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugeordnet ist.|  
|[GetExceptionThreadID-Methode](iclrdatatarget3-getexceptionthreadid-method.md)|Wird durch die CLR-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild. Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
- [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
