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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178409"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne ab, die durch diese [ICorPublishAppDomain](icorpublishappdomain-interface.md)dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Anzahl der breiten Zeichen, einschließlich `szName` des Nullzeichens, die im Array zurückgegeben werden.  
  
 `szName`  
 [out] Ein Array, in dem der Name gespeichert werden soll.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `szName` es sich um `GetName` ungleich `cchName` NULL handelt, kopiert die `szName`Methode Zeichen (einschließlich des Nullabschlusses) in . Wenn ein Nicht-NULL-Zeichen in `pcchName`zurückgegeben wird, wird die tatsächliche Anzahl der `szName` Zeichen im Namen (einschließlich des Nullabschlusses) im Array gespeichert.  
  
 Die `GetName` Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)
