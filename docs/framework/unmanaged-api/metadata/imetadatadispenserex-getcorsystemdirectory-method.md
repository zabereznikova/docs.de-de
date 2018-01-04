---
title: IMetaDataDispenserEx::GetCORSystemDirectory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetCORSystemDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e93f544e504949b496881369c15905ef43a0d2f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a>IMetaDataDispenserEx::GetCORSystemDirectory-Methode
Ruft das Verzeichnis, das die aktuelle common Language Runtime (CLR) enthält. Diese Methode ist nur für die Verwendung von Out-of-Process-Debugger unterstützt. Wenn aus einer anderen Komponente aufgerufen wird, gibt es E_NOTIMPL zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szBuffer`  
 [out] Der Puffer, der den Namen des Verzeichnisses erhalten.  
  
 `cchBuffer`  
 [in] Die Größe in Bytes, der `szBuffer`.  
  
 `pchBuffer`  
 [out] Die Anzahl der Bytes, die tatsächlich im zurückgegebenen `szBuffer`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
