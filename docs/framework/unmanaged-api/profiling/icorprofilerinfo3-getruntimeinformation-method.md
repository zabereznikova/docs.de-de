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
ms.openlocfilehash: fdb2b1601e0164de19bcc1e8f60856346aeaacb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698012"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation-Methode

Stellt Versionsinformationen über die Common Language Runtime (CLR) bereit, für die ein Profil erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 vorgenommen Die repräsentative ID einer laufenden CLR-Instanz in einem Prozess. Dies entspricht dem `ClrInstanceID` , das vom Ereignis Ablauf Verfolgungs für Windows (ETW)-Start Ereignis gemeldet wird.  
  
 `pRuntimeType`  
 vorgenommen Der Lauf Zeittyp. Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die Desktop Version der CLR zurück, oder `COR_PRF_CORE_CLR` für die in Silverlight verwendete Core-Version der CLR.  
  
 `pMajorVersion`  
 vorgenommen Die Hauptversionsnummer der CLR.  
  
 `pMinorVersion`  
 vorgenommen Die neben Versionsnummer der CLR.  
  
 `pBuildVersion`  
 vorgenommen Die Buildversionsnummer der CLR.  
  
 `pQFEVersion`  
 vorgenommen Die Versionsnummer der CLR, die einem Software Update zugeordnet ist.  
  
 `cchVersionString`  
 in Die Länge (in Zeichen) des Puffers, `szVersionString` auf den verweist.  
  
 `pcchVersionString`  
 vorgenommen Die Länge von in Zeichen `szVersionString` .  
  
 `szVersionString`  
 vorgenommen Die CLR-Versions Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  

 Sie können für jeden Parameter NULL übergeben. Kann jedoch `pcchVersionString` nicht NULL sein, es sei denn, `szVersionString` ist ebenfalls NULL.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
