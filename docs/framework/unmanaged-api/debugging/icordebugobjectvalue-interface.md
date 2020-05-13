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
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207480"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue-Schnittstelle

Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetClass-Methode](icordebugobjectvalue-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR) <xref:System.Type> des-Objekts ab, auf das dieser `ICorDebugObjectValue` verweist.|  
|[GetContext-Methode](icordebugobjectvalue-getcontext-method.md)|Nicht implementiert.|  
|[GetFieldValue-Methode](icordebugobjectvalue-getfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen [ICorDebugValue](icordebugvalue-interface.md) ab, der den Wert des angegebenen Felds der angegebenen Klasse darstellt.|  
|[GetManagedCopy-Methode](icordebugobjectvalue-getmanagedcopy-method.md)|Veraltet. Rufen Sie diese Methode nicht auf.|  
|[GetVirtualMethod-Methode](icordebugobjectvalue-getvirtualmethod-method.md)|Nicht implementiert.|  
|[IsValueClass-Methode](icordebugobjectvalue-isvalueclass-method.md)|Ruft einen Wert ab, der angibt, ob das Objekt, auf das dieser verweist, `ICorDebugObjectValue` ein Werttyp ist.|  
|[SetFromManagedCopy-Methode](icordebugobjectvalue-setfrommanagedcopy-method.md)|Veraltet. Rufen Sie diese Methode nicht auf.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugObjectValue` bleibt gültig, bis der Prozess, der debuggt wird, fortgesetzt wird.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
