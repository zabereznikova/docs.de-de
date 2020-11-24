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
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688652"
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
 in Der Wert, auf den die Eigenschaft festgelegt werden soll, auf die verweist `PropertyId` .  
  
 `cbProperty`  
 in Die Größe von in Bytes `pvProperty` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
