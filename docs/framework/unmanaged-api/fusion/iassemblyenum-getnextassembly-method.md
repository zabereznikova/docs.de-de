---
title: IAssemblyEnum::GetNextAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyEnum.GetNextAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cef1624d0432d571edfddfa772f31366e23074f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly-Methode
Ruft einen Zeiger auf dem nächsten [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) in dieser enthaltenen [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`ein null-Verweis muss sein.  
  
 `ppName`  
 [out] Das zurückgegebene `IAssemblyName` Zeiger.  
  
 `dwFlags`  
 [in] Für zukünftige Erweiterungen reserviert. `dwFlags`0 (null) muss sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [IAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
