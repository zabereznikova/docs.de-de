---
title: ICorDebugType Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de2871b406bb9da84d20d7c526ad4a703baae409
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtype-interface1"></a>ICorDebugType Schnittstelle1
Stellt einen Typ dar, entweder grundlegend oder komplex (das heißt Benutzerdefiniert ist,). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die die generische verweist <xref:System.Type> Parameter, der auf die verwiesen wird von dieser Klasse `ICorDebugType`.|  
|[GetBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ruft einen Schnittstellenzeiger auf eine `ICorDebugType` , die auf die Basisklasse der verwiesen, die von dieser Klasse verweist `ICorDebugType`, falls vorhanden.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die auf den typisierten Konstruktor dieses verweist `ICorDebugType`.|  
|[GetFirstTypeParameter-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellenzeiger auf eine `ICorDebugType` , verweist die erste generische <xref:System.Type> -Parameter für den Konstruktor der Klasse verweist, die von diesem auf `ICorDebugType`.|  
|[GetRank-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen in einen Arraytyp an.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellenzeiger einen ICorDebugValue mit dem Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld token in den angegebenen Stapelrahmen.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ruft einen CorElementType-Wert, den systemeigenen Typ der common Language Runtime beschreibt <xref:System.Type> verwiesen, die von diesem `ICorDebugType`.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ generisch ist, ist `ICorDebugClass` den nicht instanziierten Typ darstellt. Die `ICorDebugType` Schnittstelle einen instanziierten generischen Typ dar. Z. B. Hashtabellen\<K, V > dargestellt werden würde `ICorDebugClass`, wohingegen Hashtable\<Int32 "," String "> dargestellt werden würde `ICorDebugType`.  
  
 Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`. Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
