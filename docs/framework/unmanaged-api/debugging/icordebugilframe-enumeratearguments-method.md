---
title: ICorDebugILFrame::EnumerateArguments-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 474118abc505928d16737d792a619e75f1209344
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a>ICorDebugILFrame::EnumerateArguments-Methode
Ruft einen Enumerator für die Argumente in diesem Frame ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppValueEnum`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, das den Enumerator für die Argumente in diesem Frame darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateArguments`Gibt einen Enumerator zurück, der die Argumente, die in den Aufrufframe verfügbar auflisten kann, die von diesem ICorDebugILFrame-Objekt dargestellt wird. Die Liste enthält die Argumente, die [Vararg](/cpp/windows/vararg) (d. h. eine Variable Anzahl von Argumenten) sowie die Argumente, die nicht `vararg`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
