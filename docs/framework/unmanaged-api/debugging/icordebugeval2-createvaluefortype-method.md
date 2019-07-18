---
title: ICorDebugEval2::CreateValueForType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ffddb8242b6627239a99bd9223b98762910b831
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753238"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType-Methode
Ruft einen Zeiger auf einen neuen ICorDebugValue des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pType`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.  
  
 `ppValue`  
 [out] Zeiger auf die Adresse einer `ICorDebugValue` -Objekt, das den Wert darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `CreateValueForType` generalisiert [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) dadurch, dass Sie einen beliebigen Objekttyp an, einschließlich Typen konstruiert z. B. `List<int>`. Der einzige Zweck dieser Methode wird zum Generieren eines Werts, das an eine funktionsauswertung übergeben werden kann.  
  
 Der Typ muss es sich um eine Klasse oder ein Werttyp sein. Sie können nicht diese Methode verwenden, um Arraywerte oder Zeichenfolgenwerte zu erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
