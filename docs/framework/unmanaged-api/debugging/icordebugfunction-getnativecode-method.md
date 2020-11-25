---
title: ICorDebugFunction::GetNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: e34dff2ebdb6e1ea56c2682b351c3e17a44416f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726313"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode-Methode

Ruft den systemeigenen Code für die Funktion ab, die von dieser ICorDebugFunction-Instanz dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppCode`  
 vorgenommen Ein Zeiger auf die ICorDebugCode-Instanz, die den nativen Code für diese Funktion darstellt, oder NULL, wenn es sich bei dieser Funktion um MSIL-Code (Microsoft Intermediate Language) handelt, der nicht Just-in-time (JIT) kompiliert wurde.  
  
## <a name="remarks"></a>Hinweise  

 Wenn die Funktion, die durch diese Instanz dargestellt wird `ICorDebugFunction` , mehr als einmal JIT-kompiliert wurde (wie bei generischen Typen), wird `GetNativeCode` ein zufälliges System eigenes Code Objekt zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
