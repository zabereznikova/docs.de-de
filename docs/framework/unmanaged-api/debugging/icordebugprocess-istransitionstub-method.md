---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
