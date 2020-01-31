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
ms.openlocfilehash: bdc8378a129dd5bb1d9fdcb080c7b5cd53d34091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789072"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2-Schnittstelle
Eine Unterklasse von [ICLRDataTarget](iclrdatatarget-interface.md) , die von der Ebene der Datenzugriffs Dienste zum Bearbeiten virtueller Speicherbereiche im Ziel Prozess verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[AllocVirtual-Methode](iclrdatatarget2-allocvirtual-method.md)|Weist Speicher im Adressraum des Ziel Prozesses zu.|  
|[FreeVirtual-Methode](iclrdatatarget2-freevirtual-method.md)|Gibt Arbeitsspeicher frei, der zuvor im Adressraum des Ziel Prozesses zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Der API-Client (d. h. der Debugger) muss diese Schnittstelle in einer für den jeweiligen Zielprozess geeigneten Form implementieren. So hätte ein Liveprozess z. B. eine andere Implementierung als ein Speicherabbild. Das Ziel unterstützt möglicherweise keine Änderung seiner Arbeitsspeicherbereiche.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
