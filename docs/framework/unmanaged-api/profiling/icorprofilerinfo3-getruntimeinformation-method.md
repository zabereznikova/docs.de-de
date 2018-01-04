---
title: ICorProfilerInfo3::GetRuntimeInformation-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetRuntimeInformation Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eadd9970d29cc65d8411692407dcae5471e51c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation-Methode
Bietet Informationen über die common Language Runtime (CLR), die ein Profil erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pClrInstanceId`  
 [out] Die Mitarbeiter-ID einer laufenden Instanz von CLR in einem Prozess. Dies ist identisch mit der `ClrInstanceID` von Event Tracing for Windows (ETW) Startup-Ereignis gemeldet.  
  
 `pRuntimeType`  
 [out] Die Common Language Runtime-Typ. Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die Desktopversion von CLR oder `COR_PRF_CORE_CLR` für die Core-Version der CLR, die in Silverlight verwendet.  
  
 `pMajorVersion`  
 [out] Die Hauptversionsnummer der CLR.  
  
 `pMinorVersion`  
 [out] Die Nebenversionsnummer der CLR.  
  
 `pBuildVersion`  
 [out] Die Buildversionsnummer der CLR.  
  
 `pQFEVersion`  
 [out] Die Versionsnummer der CLR, die einem Softwareupdate zugeordnet ist.  
  
 `cchVersionString`  
 [in] Die Länge des Puffers in Zeichen, die `szVersionString` verweist auf.  
  
 `pcchVersionString`  
 [out] Die Länge in Zeichen, d. h. der `szVersionString`.  
  
 `szVersionString`  
 [out] Die CLR-Versionszeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Sie können null für die einzelnen Parameter übergeben. Allerdings `pcchVersionString` darf nicht null sein, wenn `szVersionString` ist ebenfalls null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
