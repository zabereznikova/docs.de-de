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
ms.openlocfilehash: 5bb41b2b49922475550997f18832b391522e2f26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137868"
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
 Wenn die Funktion, die durch diese `ICorDebugFunction` Instanz dargestellt wird, mehr als einmal JIT-kompiliert wurde, wie im Fall von generischen Typen, gibt `GetNativeCode` ein zufälliges System eigenes Code Objekt zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
