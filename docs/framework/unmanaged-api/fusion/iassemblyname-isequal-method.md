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
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712975"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual-Methode

Bestimmt basierend auf den angegebenen Vergleichsflags, ob ein angegebenes [IAssemblyName](iassemblyname-interface.md) -Objekt gleich diesem ist `IAssemblyName` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pName`  
 in Das `IAssemblyName` Objekt, mit dem dieses verglichen werden soll `IAssemblyName` .  
  
 `dwCmpFlags`  
 in Eine bitweise Kombination von [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) -Werten, die den Vergleich beeinflussen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 .Net **Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusionsenumerationen](fusion-enumerations.md)
