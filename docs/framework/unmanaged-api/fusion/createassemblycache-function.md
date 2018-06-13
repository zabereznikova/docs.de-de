---
title: CreateAssemblyCache-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba4259ad9cdf4f56fd4c00b5c7e9ebfa8b7fe1ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429578"
---
# <a name="createassemblycache-function"></a>CreateAssemblyCache-Funktion
Ruft einen Zeiger auf ein neues [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) Instanz, die im globalen Assemblycache darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppAsmCache`  
 [out] Das zurückgegebene `IAssemblyCache` Zeiger.  
  
 `dwReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `dwReserved` 0 (null) muss sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IAssemblyCache-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
