---
title: ICorPublishAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4afbc41e680d8a20166095aeb1afbc0de9bbacbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631745"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne, die von diesem dargestellt wird [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Anzahl der Breitzeichen, einschließlich des Null-Zeichen im zurückgegebenen den `szName` Array.  
  
 `szName`  
 [out] Ein Array, in dem Sie den Namen zu speichern.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `szName` nicht Null ist, wird die `GetName` -Methode kopiert bis zu `cchName` Zeichen betragen (einschließlich der null-Terminator) in `szName`. Wenn eine Wert ungleich Null, im zurückgegeben wird `pcchName`, die tatsächliche Anzahl der Zeichen im Namen (einschließlich der null-Terminator) befindet sich in der `szName` Array.  
  
 Die `GetName` Methodenrückgabe ein S_OK HRESULT unabhängig davon, wie viele Zeichen kopiert wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorPublishAppDomain-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
