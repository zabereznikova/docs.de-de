---
title: ICorDebugModule2::ResolveAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a6596807b98e6c8b8624b5df18f78dbf8d0711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417777"
---
# <a name="icordebugmodule2resolveassembly-method"></a>ICorDebugModule2::ResolveAssembly-Methode
Löst die Assembly auf, die vom angegebenen Metadatentoken verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tkAsemblyRef`  
 [in] Ein `mdToken` Wert, der die Assembly verweist.  
  
 `ppAssembly`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Assembly darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Assembly nicht bereits geladen ist `ResolveAssembly` aufgerufen wird, wird ein HRESULT Wert CORDBG_E_CANNOT_RESOLVE_ASSEMBLY zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
