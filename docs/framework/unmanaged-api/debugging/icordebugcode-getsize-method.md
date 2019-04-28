---
title: ICorDebugCode::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750206"
---
# <a name="icordebugcodegetsize-method"></a>ICorDebugCode::GetSize-Methode
Ruft die Größe des Binärcodes dargestellt durch "ICorDebugCode" in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pcBytes`  
 [out] Ein Zeiger auf die Größe in Bytes, die Binärdatei zu code, den dieses `ICorDebugCode` -Objekt darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
