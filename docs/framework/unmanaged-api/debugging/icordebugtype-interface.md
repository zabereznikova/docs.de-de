---
title: ICorDebugType-Schnittstelle
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
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166802"
---
# <a name="icordebugtype-interface"></a>ICorDebugType-Schnittstelle
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
