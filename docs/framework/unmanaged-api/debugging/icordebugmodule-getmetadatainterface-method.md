---
title: ICorDebugModule::GetMetaDataInterface-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129549"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface-Methode
Ruft ein Metadatenschnittstellenobjekt ab, das verwendet werden kann, um die Metadaten für das Modul zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `riid`  
 in Die Verweis-ID, die die Metadatenschnittstelle angibt.  
  
 `ppObj`  
 vorgenommen Ein Zeiger auf die Adresse eines `T:IUnknown` Objekts, das eine der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger kann die `GetMetaDataInterface`-Methode verwenden, um eine Kopie der ursprünglichen Metadaten für ein Modul zu erstellen. Dies ist erforderlich, um das Modul zu bearbeiten. Der Debugger ruft `GetMetaDataInterface` auf, um ein [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Schnittstellen Objekt für das Modul zu erhalten, und ruft dann [IMetaDataEmit:: SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) auf, um eine Kopie der Metadaten des Moduls in den Arbeitsspeicher zu speichern.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadaten](../../../../docs/framework/unmanaged-api/metadata/index.md)
