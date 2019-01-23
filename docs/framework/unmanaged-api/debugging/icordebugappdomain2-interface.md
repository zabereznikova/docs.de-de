---
title: ICorDebugAppDomain2-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4549b0fe6379979a7b9bd6344d65ff465f33f17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506133"
---
# <a name="icordebugappdomain2-interface1"></a>ICorDebugAppDomain2-Schnittstelle1
Stellt Methoden zum Arbeiten mit Arrays, Zeigern, Funktionszeigern und Verweistypen. Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetArrayOrPointerType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.|  
|[GetFunctionPointerType](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
