---
title: ICeeGen::EmitString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.EmitString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89c53f41595416a6bb4b8d373c7d3dbcea4c4faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iceegenemitstring-method"></a>ICeeGen::EmitString-Methode
Gibt die angegebene Zeichenfolge in die CodeBase aus.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lpString`  
 [in] Die Zeichenfolge auszugeben.  
  
 `RVA`  
 [out] Die relative virtuelle Adresse der ausgegebene Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
