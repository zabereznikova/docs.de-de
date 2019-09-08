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
ms.openlocfilehash: 926bdcee3a3c3974c8546f3a6dfe98f0b62c93c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796572"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual-Methode
Bestimmt basierend auf den angegebenen Vergleichsflags, ob ein angegebenes `IAssemblyName` [IAssemblyName](iassemblyname-interface.md) -Objekt gleich diesem ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pName`  
 in Das `IAssemblyName` Objekt, mit dem dieses `IAssemblyName`verglichen werden soll.  
  
 `dwCmpFlags`  
 in Eine bitweise Kombination von [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) -Werten, die den Vergleich beeinflussen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 .Net **Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion-Enumerationen](fusion-enumerations.md)
