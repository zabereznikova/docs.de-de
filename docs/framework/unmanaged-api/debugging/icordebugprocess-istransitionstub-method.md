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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06dc35998a2874ed1d2f76725078874817e94d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub-Methode
Ruft einen Wert, der angibt, ob eine Adresse innerhalb eines Stubs befindet, das einen Übergang zu verwaltetem Code bewirkt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Wert, der die fragliche Adresse angibt.  
  
 `pbTransitionStub`  
 [out] Ein Zeiger auf einen booleschen Wert, der `true` , wenn die angegebene Adresse innerhalb eines Stubs befindet, das bewirkt einen Übergang zu verwaltetem Code; andernfalls *`pbTransitionStub` ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die `IsTransitionStub` Methode kann von nicht verwaltetem stepping-Code verwendet werden, um zu entscheiden, wann schrittweisen Steuerung an den verwalteten zugeordnetem zurückgegeben.  
  
 Sie können auch die Identität Übergangsstubs durch einen Blick auf die Informationen in der portablen ausführbaren Datei (PE)-Datei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
