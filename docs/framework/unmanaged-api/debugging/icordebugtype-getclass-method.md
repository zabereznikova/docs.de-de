---
title: ICorDebugType::GetClass-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be9999cd0dd8db5439dd41e51429841666597b16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass-Methode
Ruft einen Schnittstellenzeiger auf eine ICorDebugClass, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppClass`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugClass` Schnittstelle, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `GetClass`kann nur unter bestimmten Umständen aufgerufen werden. Rufen Sie [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) vor dem Aufruf `GetClass`. Wenn `ICorDebugType::GetType` einen CorElementType-Wert, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE lautet, gibt `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
