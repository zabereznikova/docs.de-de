---
title: IAssemblyCache::UninstallAssembly-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
ms.openlocfilehash: 36a2a609e95740ffc45722635a7e1f09e0ed5601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670783"
---
# <a name="iassemblycacheuninstallassembly-method"></a>IAssemblyCache::UninstallAssembly-Methode

Deinstalliert die angegebene Assembly aus dem globalen Assemblycache.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwFlags`  
 in In Fusion. idl definierte Flags.  
  
 `pszAssemblyName`  
 in Der Name der zu deinstallierenden Assembly.  
  
 `pRefData`  
 in Eine [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur, die die Installationsdaten für die Assembly enthält.  
  
 `pulDisposition`  
 [out, optional] Einer der Disposition-Werte, die in Fusion. idl definiert sind. Folgende Werte sind möglich:  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)  
  
- IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyCache-Schnittstelle](iassemblycache-interface.md)
