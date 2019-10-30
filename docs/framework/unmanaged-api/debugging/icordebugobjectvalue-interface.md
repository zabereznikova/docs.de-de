---
title: ICorDebugObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129751"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-<xref:System.Type> des Objekts ab, auf das dieses `ICorDebugObjectValue` verweist.|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|Nicht implementiert.|  
|[GetFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) ab, der den Wert des angegebenen Felds der angegebenen Klasse darstellt.|  
|[GetManagedCopy-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|Veraltet. Diese Methode nicht aufzurufen.|  
|[GetVirtualMethod-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|Nicht implementiert.|  
|[IsValueClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|Ruft einen Wert ab, der angibt, ob das Objekt, auf das dieser `ICorDebugObjectValue` verweist, ein Werttyp ist.|  
|[SetFromManagedCopy-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|Veraltet. Diese Methode nicht aufzurufen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugObjectValue` bleibt gültig, bis der Prozess, der debuggt wird, fortgesetzt wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
