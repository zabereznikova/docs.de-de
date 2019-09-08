---
title: IAssemblyEnum::GetNextAssembly-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796684"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly-Methode
Ruft einen Zeiger auf den nächsten [IAssemblyName](iassemblyname-interface.md) ab, der in diesem [IAssemblyEnum](iassemblyenum-interface.md) -Objekt enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`muss ein NULL-Verweis sein.  
  
 `ppName`  
 vorgenommen Der zurück `IAssemblyName` gegebene Zeiger.  
  
 `dwFlags`  
 [in] Für zukünftige Erweiterungen reserviert. `dwFlags`muss 0 (null) sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
