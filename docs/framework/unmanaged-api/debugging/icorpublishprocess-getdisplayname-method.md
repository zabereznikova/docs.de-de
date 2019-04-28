---
title: ICorPublishProcess::GetDisplayName-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6e7aa845f104ef734f039d46e1eeaba5fd01c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704088"
---
# <a name="icorpublishprocessgetdisplayname-method"></a>ICorPublishProcess::GetDisplayName-Methode
Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, der auf die dieses [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 [out] Die Anzahl der Breitzeichen zurückgegeben, die der `szName` Array.  
  
 `szName`  
 [out] Ein Array, das den Namen, einschließlich des vollständigen Pfads, der die ausführbare Datei zu speichern. Der Name ist, Null-terminiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
