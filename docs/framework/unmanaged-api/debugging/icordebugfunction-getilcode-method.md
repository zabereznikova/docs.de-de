---
title: ICorDebugFunction::GetILCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac34fbca56c8a0f00ee3a7e0f898b8ee03287b11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412284"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode-Methode
Ruft die ICorDebugCode-Instanz, die die Microsoft intermediate Language (MSIL)-Code dieses ICorDebugFunction-Objekt zugeordnet darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppCode`  
 [out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Bearbeiten und Fortfahren wurde zugelassen. für diese Funktion die `GetILCode` Methode den MSIL-Code entspricht diese Funktion bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
