---
title: ICoreClrDebugTarget::FreeMemory-Methode
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 061a2b9990d4b4d6398d0a31b97bc403a5f10de4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397172"
---
# <a name="icoreclrdebugtargetfreememory-method"></a>ICoreClrDebugTarget::FreeMemory-Methode
Gibt den von der [icoreclrdebugtarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) -Methode und der [icoreclrdebugtarget:: enumruntimes](icoreclrdebugtarget-enumruntimes-method.md) -Methode zugeordneten Arbeitsspeicher frei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a>Parameter  
 `pMemory`  
 in Ein Zeiger auf das Array, das entweder von der [icoreclrdebugtarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) -Methode oder der [icoreclrdebugtarget:: enumruntimes](icoreclrdebugtarget-enumruntimes-method.md) -Methode zurückgegeben wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86. dll  
  
 **.NET Framework Versionen:** 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICoreClrDebugTarget-Schnittstelle](icoreclrdebugtarget-interface.md)
