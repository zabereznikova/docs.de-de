---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139388"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub-Methode
Ruft einen Wert ab, der angibt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 in Ein `CORDB_ADDRESS`-Wert, der die betreffende Adresse angibt.  
  
 `pbTransitionStub`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der `true` wird, wenn sich die angegebene Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht. Andernfalls *`pbTransitionStub` `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die `IsTransitionStub`-Methode kann von nicht verwaltetem Schritt Code verwendet werden, um zu entscheiden, wann die schrittweise Steuerung an den verwalteten Stepper zurückgegeben werden soll.  
  
 Sie können auch die übergangsstubübereinstisstubweise überprüfen, indem Sie die Informationen in der Datei "Portable  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
