---
title: ICorDebugModule::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 0cfc31839b263c2e8cf44d15439b44ffacccf5bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709894"
---
# <a name="icordebugmodulegetsize-method"></a>ICorDebugModule::GetSize-Methode

Ruft die Größe des Moduls in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pcBytes`  
 vorgenommen Die Größe des Moduls in Bytes.  
  
 Wenn das Modul aus dem nativen Image Generator (NGen.exe) erstellt wurde, ist die Größe des Moduls 0 (null).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
