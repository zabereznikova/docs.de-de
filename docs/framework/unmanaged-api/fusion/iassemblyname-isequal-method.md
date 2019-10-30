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
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134303"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual-Methode
Bestimmt, ob ein angegebenes [IAssemblyName](iassemblyname-interface.md) -Objekt auf Grundlage der angegebenen Vergleichsflags gleich diesem `IAssemblyName`ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pName`  
 in Das `IAssemblyName` Objekt, mit dem diese `IAssemblyName`verglichen werden soll.  
  
 `dwCmpFlags`  
 in Eine bitweise Kombination von [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) -Werten, die den Vergleich beeinflussen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 .Net **Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion-Enumerationen](fusion-enumerations.md)
