---
title: IAssemblyName::GetProperty-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: b86828e01fb00b12feff2ed451793c240e16e240
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134383"
---
# <a name="iassemblynamegetproperty-method"></a>IAssemblyName::GetProperty-Methode
Ruft einen Zeiger auf die Eigenschaft ab, auf die durch den angegebenen Eigenschaften Bezeichner verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `PropertyId`  
 in Der eindeutige Bezeichner für die angeforderte Eigenschaft.  
  
 `pvProperty`  
 vorgenommen Die zurückgegebenen Eigenschafts Daten.  
  
 `pcbProperty`  
 [in, out] Die Größe `pvProperty`in Byte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
