---
title: ICorDebugMergedAssemblyRecord::GetVersion-Methode
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 7352a77fc8f41124d7e6c78a3dfc6ccd6d3a94aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710505"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>ICorDebugMergedAssemblyRecord::GetVersion-Methode

Ruft Versionsinformationen zur Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pMajor`  
 [out] Ein Zeiger auf die Hauptversionsnummer.  
  
 `pMinor`  
 [out] Ein Zeiger auf die Nebenversionsnummer.  
  
 `pBuild`  
 [out] Ein Zeiger auf die Buildnummer.  
  
 `pRevision`  
 [out] Ein Zeiger auf die Revisionsnummer.  
  
## <a name="remarks"></a>Hinweise  

 Informationen zu den Versionsnummern von Assemblys finden Sie im Thema zur <xref:System.Version>-Klasse.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMergedAssemblyRecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
