---
title: ICorDebugChain::GetStackRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: d9430c5a1f37a0507b383ea5437f7d7fed706c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123863"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange-Methode
Ruft den Adressbereich des Stapel Segments für diese Kette ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pStart`  
 vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS`-Wert, der die Startadresse des Stapel Segments ist.  
  
 `pEnd`  
 vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` Wert, der die Endadresse des Stapel Segments ist.  
  
## <a name="remarks"></a>Hinweise  
 Der numerische Bereich ist nur für den Vergleich von Stapel Rahmen Positionen sinnvoll. Sie können keine Annahmen darüber treffen, was tatsächlich im Stapel gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
