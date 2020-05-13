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
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213620"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode-Methode
Ruft die ICorDebugCode-Instanz ab, die den MSIL-Code (Microsoft Intermediate Language) darstellt, der mit diesem ICorDebugFunction-Objekt verknüpft ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppCode`  
 vorgenommen Ein Zeiger auf die- `ICorDebugCode` Instanz oder NULL, wenn die Funktion nicht in MSIL kompiliert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn "Bearbeiten und Fortfahren" für diese Funktion zulässig ist, erhält die `GetILCode` Methode den MSIL-Code, der der bearbeiteten Version des Codes der Funktion in der Common Language Runtime (CLR) entspricht.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
