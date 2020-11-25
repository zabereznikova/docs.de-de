---
title: ICorDebugModule::GetToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 6ffc74247a4ecafcc3744923c0def99220b5ca6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709881"
---
# <a name="icordebugmodulegettoken-method"></a>ICorDebugModule::GetToken-Methode

Ruft das Token für den Tabelleneintrag für dieses Modul ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pToken`  
 vorgenommen Ein Zeiger auf das `mdModule` Token, das auf die Metadaten des Moduls verweist.  
  
## <a name="remarks"></a>Hinweise  

 Das Token kann an die Metadatenimport-Schnittstellen [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)und [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) übermittelt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadaten](../metadata/index.md)
