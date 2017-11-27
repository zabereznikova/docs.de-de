---
title: ICorProfilerInfo::GetILFunctionBody-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6908b6c765a56ef0aa43a66cc58ec74b525bc2d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody-Methode
Ruft einen Zeiger auf den Text einer Methode in Microsoft intermediate Language (MSIL)-Code, beginnend mit dem Header.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, in dem die Funktion befindet.  
  
 `methodId`  
 [in] Das Metadatentoken für die Methode.  
  
 `ppMethodHeader`  
 [out] Ein Zeiger auf die Method-Header.  
  
 `pcbMethodSize`  
 [out] Eine ganze Zahl, die die Größe der Methode angibt.  
  
## <a name="remarks"></a>Hinweise  
 Eine Methode wird vom Modul begrenzt, in dem er sich befindet. Da die `GetILFunctionBody` -Methode entwickelt, um MSIL-Code eine Toolzugriff erteilen, bevor er von der common Language Runtime (CLR) geladen wurde, es verwendet das Metadatentoken der Methode, um die gewünschte Instanz gefunden werden.  
  
 `GetILFunctionBody`kann ein HRESULT CORPROF_E_FUNCTION_NOT_IL zurückgeben, wenn die `methodId` verweist auf eine Methode ohne MSIL-code (z. B. eine abstrakte Methode oder eine Plattform invoke PInvoke-Methode).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
