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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac0e5db4a87b49d631bad4411f03fae8c1199aea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125631"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler-Methode
Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neuzuordnungen von Adressen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pUnk`  
 [in] Der Handler zu registrieren.  
  
## <a name="remarks"></a>Hinweise  
 Die Metadaten-Engine sendet Benachrichtigung mithilfe der Methode, die von bereitgestellte `SetHandler`, um den Compiler, die Datensätze nicht auf optimierte Weise generieren und die gespeicherte Datensätze optimieren möchten.  
  
 Wenn die Callback-Methode nicht über die bereitgestellten `SetHandler`, keine Optimierung erfolgt auf Speichern mit Ausnahme von denen einige importieren Bereiche zusammengeführt wurden mithilfe von `IMapToken` auf Merge für jeden Bereich.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
