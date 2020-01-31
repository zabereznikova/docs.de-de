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
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792687"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetClass-Methode](icordebugobjectvalue-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-<xref:System.Type> des Objekts ab, auf das dieses `ICorDebugObjectValue` verweist.|  
|[GetContext-Methode](icordebugobjectvalue-getcontext-method.md)|Nicht implementiert.|  
|[GetFieldValue-Methode](icordebugobjectvalue-getfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen [ICorDebugValue](icordebugvalue-interface.md) ab, der den Wert des angegebenen Felds der angegebenen Klasse darstellt.|  
|[GetManagedCopy-Methode](icordebugobjectvalue-getmanagedcopy-method.md)|Veraltet. Diese Methode nicht aufzurufen.|  
|[GetVirtualMethod-Methode](icordebugobjectvalue-getvirtualmethod-method.md)|Nicht implementiert.|  
|[IsValueClass-Methode](icordebugobjectvalue-isvalueclass-method.md)|Ruft einen Wert ab, der angibt, ob das Objekt, auf das dieser `ICorDebugObjectValue` verweist, ein Werttyp ist.|  
|[SetFromManagedCopy-Methode](icordebugobjectvalue-setfrommanagedcopy-method.md)|Veraltet. Diese Methode nicht aufzurufen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugObjectValue` bleibt gültig, bis der Prozess, der debuggt wird, fortgesetzt wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
