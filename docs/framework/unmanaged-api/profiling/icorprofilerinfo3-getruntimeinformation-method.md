---
title: ICorProfilerInfo3::GetRuntimeInformation-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000596"
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
  
## <a name="parameters"></a>Parameter  
 `pClrInstanceId`  
 [out] Die Mitarbeiter-ID einer laufenden Instanz von CLR in einem Prozess. Dies ist identisch mit der `ClrInstanceID` , dass die ereignisablaufverfolgung für Windows (ETW)-Startup-Ereignis meldet.  
  
 `pRuntimeType`  
 [out] Der Common Language Runtime-Typ. Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die desktop-Version der CLR oder `COR_PRF_CORE_CLR` für die Core-Version der CLR in Silverlight verwendet.  
  
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
 [out] Die Länge in Zeichen des `szVersionString`.  
  
 `szVersionString`  
 [out] Die CLR-Versionszeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Sie können für jeden Parameter null übergeben. Allerdings `pcchVersionString` darf nicht null sein, wenn `szVersionString` ist ebenfalls null.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
