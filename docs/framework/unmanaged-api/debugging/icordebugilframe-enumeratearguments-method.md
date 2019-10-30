---
title: ICorDebugILFrame::EnumerateArguments-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131032"
---
# <a name="icordebugilframeenumeratearguments-method"></a>ICorDebugILFrame::EnumerateArguments-Methode
Ruft einen Enumerator für die Argumente in diesem Frame ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppValueEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalueenum-Objekts, das der Enumerator für die Argumente in diesem Frame ist.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateArguments` Ruft einen Enumerator ab, der die Argumente auflisten kann, die in dem von diesem ICorDebugILFrame-Objekt dargestellten callframe verfügbar sind. Die Liste enthält Argumente, die [vararg](/cpp/windows/vararg) sind (d. h. eine Variable Anzahl von Argumenten), sowie Argumente, die nicht `vararg`sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
