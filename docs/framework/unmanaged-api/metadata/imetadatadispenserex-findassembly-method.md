---
title: IMetaDataDispenserEx::FindAssembly-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713391"
---
# <a name="imetadatadispenserexfindassembly-method"></a>IMetaDataDispenserEx::FindAssembly-Methode

Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szAppBase`  
 [in] Wird nicht verwendet.  
  
 `szPrivateBin`  
 [in] Wird nicht verwendet.  
  
 `szGlobalBin`  
 [in] Wird nicht verwendet.  
  
 `szAssemblyName`  
 in Die Assembly, die gefunden werden soll.  
  
 `szName`  
 vorgenommen Der einfache Name der Assembly.  
  
 `cchName`  
 in Die Größe von in Bytes `szName` .  
  
 `pcName`  
 vorgenommen Die Anzahl der Zeichen, die tatsächlich in zurückgegeben werden `szName` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenserEx-Schnittstelle](imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md)
