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
ms.openlocfilehash: 9693014a24c5cbbb0db2d1c9b0a4d41fd3cdf5b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710044"
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
 vorgenommen Ein Zeiger auf die Adresse eines `T:IUnknown` Objekts, das eine der [Metadatenschnittstellen](../metadata/metadata-interfaces.md)ist.  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger kann die- `GetMetaDataInterface` Methode verwenden, um eine Kopie der ursprünglichen Metadaten für ein Modul zu erstellen. Dies ist erforderlich, um das Modul zu bearbeiten. Der Debugger ruft `GetMetaDataInterface` auf, um ein [IMetaDataEmit](../metadata/imetadataemit-interface.md) -Schnittstellen Objekt für das Modul zu erhalten, und ruft dann [IMetaDataEmit:: SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) auf, um eine Kopie der Metadaten des Moduls in den Arbeitsspeicher zu speichern.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadaten](../metadata/index.md)
