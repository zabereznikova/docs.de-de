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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 499f58cc0a3f2d1b3c159435ed7d9b523f25e29e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757891"
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
 [out] Ein Zeiger auf die Adresse des ICorDebugValueEnum-Objekts, das den Enumerator für die Argumente in diesem Frame ist.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateArguments` Ruft einen Enumerator aus, der den Argumenten, die in den Aufrufframe auflisten kann, die von diesem ICorDebugILFrame-Objekt dargestellt wird. Die Liste enthält Argumente, die sind [Vararg](/cpp/windows/vararg) (d. h. eine Variable Anzahl von Argumenten) sowie Argumente, die nicht `vararg`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
