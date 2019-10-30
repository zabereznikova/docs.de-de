---
title: ICorDebugType::GetType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132063"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType-Methode
Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des von diesem ICorDebugType dargestellten Common Language Runtime (CLR) <xref:System.Type> beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ty`  
 vorgenommen Ein Zeiger auf einen Wert der `CorElementType`-Enumeration, die die CLR-<xref:System.Type> angibt, die dieser `ICorDebugType` darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert `ty` entweder "ELEMENT_TYPE_CLASS" oder "ELEMENT_TYPE_VALUETYPE" ist, kann die [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) -Methode aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten. Andernfalls sollten Sie `ICorDebugType::GetClass`nicht aufzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
