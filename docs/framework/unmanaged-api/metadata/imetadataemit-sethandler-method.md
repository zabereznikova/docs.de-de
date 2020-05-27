---
title: IMetaDataEmit::SetHandler-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003938"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler-Methode
Legt die Methode, auf die der angegebene Zeiger verweist, `IUnknown` als Benachrichtigungs Rückruf für die Tokenneuzuordnung fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pUnk`  
 in Der zu Registrier gende Handler.  
  
## <a name="remarks"></a>Hinweise  
 Die metadatenengine sendet mithilfe der von bereitgestellten Methode eine Benachrichtigung `SetHandler` an Compiler, die keine Datensätze auf optimierte Weise generieren und gespeicherte Datensätze optimieren möchten.  
  
 Wenn die Rückruf Methode nicht mithilfe von bereitgestellt wird `SetHandler` , wird beim Speichern nur dann eine Optimierung durchgeführt, wenn mehrere Import Bereiche mithilfe `IMapToken` von bei Merge für jeden Bereich zusammengeführt wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
