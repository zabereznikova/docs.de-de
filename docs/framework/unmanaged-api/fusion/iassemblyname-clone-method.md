---
title: IAssemblyName::Clone-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
ms.openlocfilehash: 1236a574a85c01e3e1be5df9644bd04bbf0753ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134405"
---
# <a name="iassemblynameclone-method"></a>IAssemblyName::Clone-Methode
Erstellt eine flache Kopie dieses [IAssemblyName](iassemblyname-interface.md) -Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pName`  
 vorgenommen Die zurückgegebene Kopie dieses `IAssemblyName` Objekts.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
