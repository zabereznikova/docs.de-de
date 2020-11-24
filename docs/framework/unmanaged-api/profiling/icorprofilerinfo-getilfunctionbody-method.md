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
ms.openlocfilehash: 337c4fd091ebf7c39f7eee2358ca4f4df239cce3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687527"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody-Methode

Ruft einen Zeiger auf den Text einer Methode im MSIL-Code (Microsoft Intermediate Language) ab, beginnend bei der Kopfzeile.  
  
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
 in Die ID des Moduls, in dem sich die Funktion befindet.  
  
 `methodId`  
 in Das Metadatentoken für die Methode.  
  
 `ppMethodHeader`  
 vorgenommen Ein Zeiger auf den-Header der Methode.  
  
 `pcbMethodSize`  
 vorgenommen Eine ganze Zahl, die die Größe der Methode angibt.  
  
## <a name="remarks"></a>Hinweise  

 Eine Methode wird durch das Modul festgelegt, in dem Sie sich befindet. Da die- `GetILFunctionBody` Methode so konzipiert ist, dass ein Tool Zugriff auf den MSIL-Code erhält, bevor Sie von der Common Language Runtime (CLR) geladen wurde, wird das Metadatentoken der-Methode verwendet, um die gewünschte Instanz zu suchen.  
  
 `GetILFunctionBody` kann eine CORPROF_E_FUNCTION_NOT_IL HRESULT zurückgeben, wenn `methodId` auf eine Methode ohne MSIL-Code verweist (z. b. eine abstrakte Methode oder eine Platt Form Aufruf Methode (PInvoke)).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
