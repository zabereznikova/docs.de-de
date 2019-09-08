---
title: IInstallReferenceItem::GetReference-Methode
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9395fcc6d896114c25770edbc17761323285099f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796395"
---
# <a name="iinstallreferenceitemgetreference-method"></a>IInstallReferenceItem::GetReference-Methode
Ruft einen Zeiger auf die [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur ab, die durch dieses [IInstallReferenceItem](iinstallreferenceitem-interface.md) -Objekt dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppRefData`  
 vorgenommen Der zurück `FUSION_INSTALL_REFERENCE` gegebene Zeiger.  
  
 `dwFlags`  
 [in] Für zukünftige Erweiterungen reserviert. `dwFlags`muss 0 (null) sein.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`muss ein NULL-Verweis sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IInstallReferenceItem-Schnittstelle](iinstallreferenceitem-interface.md)
- [FUSION_INSTALL_REFERENCE-Struktur](fusion-install-reference-structure.md)
