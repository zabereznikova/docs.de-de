---
title: ICorDebugDataTarget2::GetImageLocation-Methode
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 348c51507006fecfe756cb17fd0d6242617577d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750223"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>ICorDebugDataTarget2::GetImageLocation-Methode
Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `baseAddress`  
 [in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der Basisadresse des Moduls darstellt.  
  
 `cchName`  
 [in] Die Anzahl der Zeichen im Puffer, die den Modulpfad erhalten sollen.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Anzahl der in den `szName`-Puffer geschriebenen Zeichen.  
  
 `szName`  
 [out] Der Pfad des Moduls.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
