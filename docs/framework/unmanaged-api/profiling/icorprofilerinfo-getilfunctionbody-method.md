---
title: ICorProfilerInfo::GetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 484fb5b8398e3ebd61d1c300afec1536ee1dc0c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780603"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody-Methode
Ruft einen Zeiger auf den Text einer Methode in Microsoft intermediate Language (MSIL)-Code, beginnend mit dem Header an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, in dem die Funktion befindet.  
  
 `methodId`  
 [in] Das Metadatentoken für die Methode.  
  
 `ppMethodHeader`  
 [out] Ein Zeiger auf den Header der Methode.  
  
 `pcbMethodSize`  
 [out] Eine ganze Zahl, die die Größe der Methode angibt.  
  
## <a name="remarks"></a>Hinweise  
 Eine Methode ist das Modul beschränkt, in dem er sich befindet. Da die `GetILFunctionBody` -Methode entwickelt, um den MSIL-Code eine Toolzugriff gewähren, bevor es von der common Language Runtime (CLR) geladen wurde, es verwendet das Metadatentoken der Methode aus, um die gewünschte Instanz zu suchen.  
  
 `GetILFunctionBody` kann ein CORPROF_E_FUNCTION_NOT_IL HRESULT zurückgeben, wenn die `methodId` verweist auf eine Methode ohne MSIL-code (z. B. PInvoke-Methode aufrufen, eine abstrakte Methode oder eine Plattform).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
