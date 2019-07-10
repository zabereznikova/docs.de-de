---
title: ICorDebugFrame::GetStackRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754851"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange-Methode
Ruft den Bereich der absoluten Adresse dieses Stapelrahmens ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pStart`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Startadresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame` Objekt.  
  
 `pEnd`  
 [out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Endadresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame` Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Adressbereich des Stapels eignet sich für die Zusammenführung von mehrere Debug-Engines erfassten stapelüberwachungen überlappender. Der numerische Bereich bietet keine Informationen über den Inhalt des Stapelrahmens. Es ist sinnvoll, nur für den Vergleich der Stack-Frame-Standorte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
