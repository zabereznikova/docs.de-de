---
title: IMetaDataEmit2::GetDeltaSaveSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 36021333c1efb61e23c16782d8ad721de62c2643
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674319"
---
# <a name="imetadataemit2getdeltasavesize-method"></a>IMetaDataEmit2::GetDeltaSaveSize-Methode

Ruft einen Wert ab, der eine Änderung der Metadatengröße angibt, die sich aus der aktuellen Sitzung zum Bearbeiten und Fortfahren ergibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `fSave`  
 in Einer der [CorSaveSize](corsavesize-enumeration.md) -Werte, der den gewünschten Genauigkeits Grad angibt. Bei der .NET Framework-Version 2,0 wird dieser Parameter ignoriert.  
  
 `pdwSaveSize`  
 vorgenommen Die Änderung der Größe der Metadaten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
