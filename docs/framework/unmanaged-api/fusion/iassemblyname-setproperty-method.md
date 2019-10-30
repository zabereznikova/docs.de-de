---
title: IAssemblyName::SetProperty-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108220"
---
# <a name="iassemblynamesetproperty-method"></a>IAssemblyName::SetProperty-Methode
Legt den Wert der Eigenschaft fest, auf die durch den angegebenen Eigenschaften Bezeichner verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `PropertyId`  
 in Der eindeutige Bezeichner der Eigenschaft, deren Wert festgelegt wird.  
  
 `pvProperty`  
 in Der Wert, auf den die Eigenschaft festgelegt werden soll, auf die `PropertyId`verweist.  
  
 `cbProperty`  
 in Die Größe `pvProperty`in Byte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
