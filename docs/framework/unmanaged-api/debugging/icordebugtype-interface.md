---
title: ICorDebugType-Schnittstelle1
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
ms.openlocfilehash: d29ab3c67e0788b15850b7dfb8b55914c1d1e369
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694528"
---
# <a name="icordebugtype-interface1"></a>ICorDebugType-Schnittstelle1
Stellt einen Typ dar, entweder grundlegend oder komplex (das heißt Benutzerdefiniert,). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellenzeiger auf eine ICorDebugTypeEnum, die die generische verweist <xref:System.Type> Parameter, der auf die verwiesen wird von dieser Klasse `ICorDebugType`.|  
|[GetBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` , die auf die Basisklasse der Klasse auf die dieses `ICorDebugType`, sofern vorhanden.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die den typisierten Konstruktor dieser verweist `ICorDebugType`.|  
|[GetFirstTypeParameter-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellenzeiger auf ein `ICorDebugType` , die auf dem ersten generischen <xref:System.Type> Parameter für den Konstruktor der Klasse auf die dieses `ICorDebugType`.|  
|[GetRank-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen im Array-Typ ab.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellenzeiger auf einen mit dem Wert des statischen Felds auf die verwiesen wird durch das angegebene Feld ICorDebugValue-Tokens in den angegebenen Stapelrahmen.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ruft einen CorElementType-Wert, der den systemeigenen Typ des von der common Language Runtime beschreibt <xref:System.Type> verwiesen, die von diesem `ICorDebugType`.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ generisch ist, ist `ICorDebugClass` den nicht instanziierten Typ darstellt. Die `ICorDebugType` Schnittstelle stellt einen instanziierten generischen Typ dar. Z. B. Hashtable\<K, V > durch dargestellt werden würde `ICorDebugClass`hingegen Hashtable\<Int32, Zeichenfolge > durch dargestellt werden würde `ICorDebugType`.  
  
 Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`. Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
