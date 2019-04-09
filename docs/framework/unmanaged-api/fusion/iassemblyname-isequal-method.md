---
title: IAssemblyName::IsEqual-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081514"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual-Methode
Bestimmt, ob ein angegebener [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt gleich diesem ist `IAssemblyName`basierend auf den angegebenen Vergleichsflags.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pName`  
 [in] Die `IAssemblyName` Objekts, dem der Vergleich `IAssemblyName`.  
  
 `dwCmpFlags`  
 [in] Eine bitweise Kombination von [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) Werte, die den Vergleich beeinflussen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Fusionsenumerationen](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
