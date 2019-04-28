---
title: IInstallReferenceEnum::GetNextInstallReferenceItem-Methode
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757936"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>IInstallReferenceEnum::GetNextInstallReferenceItem-Methode
Ruft einen Zeiger auf der nächste [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) Objekt enthalten, die in diesem [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppRefItem`  
 [out] Das zurückgegebene `IInstallReferenceItem` Zeiger.  
  
 `dwFlags`  
 [in] Für zukünftige Erweiterungen reserviert. `dwFlags` 0 (null) muss sein.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` ein null-Verweis muss sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IInstallReferenceItem-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [IInstallReferenceEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
