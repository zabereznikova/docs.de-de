---
title: ICorDebugRegisterSet::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 63ddce2f299133fcfe0da17897eaf0c6a9509a55
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378243"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext-Methode
`SetThreadContext`ist nicht in der .NET Framework Version 2,0 implementiert. Rufen Sie diese Methode nicht auf.  
  
> [!NOTE]
> Verwenden Sie den übergeordneten Vorgang [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) , um den Kontext eines Threads festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)
