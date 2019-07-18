---
title: ICorDebugFunction::GetNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754597"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode-Methode
Ruft den systemeigenen Code für die Funktion, die von dieser Instanz ICorDebugFunction dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppCode`  
 [out] Ein Zeiger auf die ICorDebugCode-Instanz, die den nativen Code für diese Funktion, oder Null, darstellt, wenn diese Funktion Microsoft intermediate Language (MSIL)-Code, die nicht mit just ist-in-Time (JIT) kompiliert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz wurde mit JIT kompiliert wurden mehr als einmal als im Fall von generischen Typen `GetNativeCode` gibt eine zufällige systemeigenen Code-Objekt zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
