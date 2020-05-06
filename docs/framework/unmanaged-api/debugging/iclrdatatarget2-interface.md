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
ms.openlocfilehash: 6b2700b2f12e312f06640a06e5ec82fbc58f2ca9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860462"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2-Schnittstelle
Eine Unterklasse von [ICLRDataTarget](iclrdatatarget-interface.md) , die von der Ebene der Datenzugriffs Dienste zum Bearbeiten virtueller Speicherbereiche im Ziel Prozess verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AllocVirtual-Methode](iclrdatatarget2-allocvirtual-method.md)|Weist Speicher im Adressraum des Ziel Prozesses zu.|  
|[FreeVirtual-Methode](iclrdatatarget2-freevirtual-method.md)|Gibt Arbeitsspeicher frei, der zuvor im Adressraum des Ziel Prozesses zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild. Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
