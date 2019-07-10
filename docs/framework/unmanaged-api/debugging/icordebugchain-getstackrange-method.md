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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745687"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange-Methode
Ruft den Adressbereich des Stack-Segments für diese Kette ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pStart`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Startadresse des Stack-Segments.  
  
 `pEnd`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` Wert, der die Endadresse des Stack-Segments.  
  
## <a name="remarks"></a>Hinweise  
 Der numerische Bereich ist nur für den Vergleich der Stack-Frame-Standorte von Bedeutung. Sie können keine Annahmen über was tatsächlich auf dem Stapel gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
