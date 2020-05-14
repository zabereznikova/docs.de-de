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
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396296"
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
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, einschließlich des NULL-Zeichens, das im Array zurückgegeben wird `szName` .  
  
 `szName`  
 vorgenommen Ein Array, in dem der Name gespeichert werden soll.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn ungleich `szName` NULL ist, kopiert die `GetName` Methode bis zu `cchName` Zeichen (einschließlich des NULL-Terminator) in `szName` . Wenn ein nicht-NULL-Wert in zurückgegeben wird `pcchName` , wird die tatsächliche Anzahl von Zeichen im Namen (einschließlich des NULL-Abschluss Zeichens) im- `szName` Array gespeichert.  
  
 Die- `GetName` Methode gibt eine S_OK HRESULT zurück, unabhängig davon, wie viele Zeichen kopiert wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)
