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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790705"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne ab, die von dieser [ICorPublishAppDomain](icorpublishappdomain-interface.md)dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, einschließlich des NULL-Zeichens, die im `szName` Array zurückgegeben werden.  
  
 `szName`  
 vorgenommen Ein Array, in dem der Name gespeichert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `szName` ungleich NULL ist, kopiert die Methode `GetName` bis zu `cchName` Zeichen (einschließlich des NULL-Terminator) in `szName`. Wenn ein nicht-NULL-Wert in `pcchName`zurückgegeben wird, wird die tatsächliche Anzahl der Zeichen im Namen (einschließlich des NULL-Terminator) im `szName` Array gespeichert.  
  
 Die `GetName`-Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)
