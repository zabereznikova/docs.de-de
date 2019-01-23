---
title: ICorDebugNativeFrame-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c923b54f791cd8ff794538d4687ca0329e62c87e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547026"
---
# <a name="icordebugnativeframe-interface1"></a>ICorDebugNativeFrame-Schnittstelle1
Eine spezielle Implementierung der ICorDebugFrame für systemeigene Rahmen verwendet werden soll.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Ruft einen Wert, der angibt, ob den Anweisungszeiger im nativen Code auf die angegebenen Offsetposition festgelegt werden kann.|  
|[GetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Ruft den Offset des Stapelrahmens in nativen Code ab.|  
|[GetLocalDoubleRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ruft einen Zeiger auf ICorDebugValue ab, der den Wert des Arguments oder einer lokalen Variablen gespeichert, die in zwei Speicher-Register, der ein nativer Frame darstellt.|  
|[GetLocalMemoryRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die die niedrigen Bits im angegebenen Register gespeichert sind, und die oberen Bits werden auf der angegebenen Speicheradresse gespeichert darstellt.|  
|[GetLocalMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die an der angegebenen Speicheradresse gespeichert darstellt.|  
|[GetLocalRegisterMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die die oberen Bits werden im angegebenen Register gespeichert, und die niedrigen Bits werden auf der angegebenen Speicheradresse gespeichert darstellt.|  
|[GetLocalRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert eines Arguments oder eine lokale Variable, die in der angegebenen systemeigenen Register gespeichert darstellt.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Ruft einen Zeiger auf ein [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , das darstellt, des Registers, legen Sie für dieses `ICorDebugNativeFrame`.|  
|[SetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Legt den Anweisungszeiger auf die angegebenen Offsetposition in systemeigenem Code fest.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
