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
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964763"
---
# <a name="icordebugtype-interface"></a>ICorDebugType-Schnittstelle
Stellt einen Typ dar, entweder "Basic" oder "Complex" (d. h. Benutzer definiert). Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateTypeParameters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die auf <xref:System.Type> die generischen Parameter der Klasse verweist `ICorDebugType`, auf die von verwiesen wird.|  
|[GetBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` -Wert ab, der auf die Basisklasse der Klasse `ICorDebugType`verweist, auf die diese verweist, sofern vorhanden.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die auf den typisierten Konstruktor von `ICorDebugType`verweist.|  
|[GetFirstTypeParameter-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugType` ab, der auf den <xref:System.Type> ersten generischen Parameter für den Konstruktor der Klasse verweist `ICorDebugType`, auf die von verwiesen wird.|  
|[GetRank-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ruft die Anzahl der Dimensionen in einem Arraytyp ab.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebugValue ab, der den Wert des statischen Felds enthält, auf das durch das angegebene Feld Token im angegebenen Stapel Rahmen verwiesen wird.|  
|[GetType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ruft einen korelementtype-Wert ab, der den systemeigenen Typ <xref:System.Type> des Common Language Runtime beschreibt `ICorDebugType`, auf den von diesem verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ generisch ist `ICorDebugClass` , stellt den nicht instanziierten Typ dar. Die `ICorDebugType` -Schnittstelle stellt einen instanziierten generischen Typ dar. Beispielsweise würde Hashtable\<K, V > durch `ICorDebugClass`dargestellt, wohingegen Hash Table\<Int32, Zeichen folgen > durch `ICorDebugType`dargestellt werden.  
  
 Nicht generische Typen werden sowohl `ICorDebugClass` von als auch `ICorDebugType`von dargestellt. Die zweite Schnittstelle wurde in der .NET Framework Version 2,0 eingeführt, um die Typinstanziierung zu behandeln.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
