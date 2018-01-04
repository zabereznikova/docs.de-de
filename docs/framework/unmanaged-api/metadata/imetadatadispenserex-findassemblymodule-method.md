---
title: IMetaDataDispenserEx::FindAssemblyModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssemblyModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 482bc9b9a89d876e7ac09fcb4edcd190adc168f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a>IMetaDataDispenserEx::FindAssemblyModule-Methode
Diese Methode ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szAppBase`  
 [in] Nicht verwendet.  
  
 `szPrivateBin`  
 [in] Nicht verwendet.  
  
 `szGlobalBin`  
 [in] Nicht verwendet.  
  
 `szAssemblyName`  
 [in] Der Name des Moduls.  
  
 `szModuleName`  
 [in] Die Assembly gefunden werden.  
  
 `szName`  
 [out] Der einfache Name der Assembly.  
  
 `cchName`  
 [in] Die Größe in Bytes, der `szName`.  
  
 `pcName`  
 [out] Die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `szName`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
