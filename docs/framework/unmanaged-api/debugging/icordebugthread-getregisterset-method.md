---
title: ICorDebugThread::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 606453424d34dcb22716c308d210fb257d1c37a7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378866"
---
# <a name="icordebugthreadgetregisterset-method"></a>ICorDebugThread::GetRegisterSet-Methode
Ruft einen Schnittstellen Zeiger auf den Register Satz ab, der dem aktiven Teil dieses ICorDebugThread-Objekts zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppRegisters`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICorDebugRegisterSet](icordebugregisterset-interface.md) -Schnittstellen Objekts, das den Register Satz für den aktiven Teil dieses Threads darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
