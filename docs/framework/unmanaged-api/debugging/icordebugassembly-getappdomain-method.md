---
title: ICorDebugAssembly::GetAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 55a798bcc575aee3f309c35eb454a0675e0cbd97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734074"
---
# <a name="icordebugassemblygetappdomain-method"></a>ICorDebugAssembly::GetAppDomain-Methode

Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppAppDomain`  
 vorgenommen Ein Zeiger auf die Adresse einer ICorDebugAppDomain-Schnittstelle, die die Anwendungsdomäne darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Wenn diese Assembly die Systemassembly ist, `GetAppDomain` gibt NULL zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
