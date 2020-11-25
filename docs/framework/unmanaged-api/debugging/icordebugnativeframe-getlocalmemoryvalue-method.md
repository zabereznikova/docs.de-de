---
title: ICorDebugNativeFrame::GetLocalMemoryValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: 92a4ee2007760024b5802208d77ca3abc81e3cf3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695672"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryValue-Methode

Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das an der angegebenen Speicheradresse für diesen systemeigenen Frame gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 in Ein- `CORDB_ADDRESS` Wert, der den Speicherort angibt, der den Wert enthält.  
  
 `cbSigBlob`  
 in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .  
  
 `pvSigBlob`  
 in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der an der angegebenen Speicheradresse gespeichert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
