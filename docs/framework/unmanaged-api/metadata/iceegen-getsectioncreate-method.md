---
title: ICeeGen::GetSectionCreate-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93e96e7804a3b5ecc64e9e50ce700435be83b77a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643363"
---
# <a name="iceegengetsectioncreate-method"></a>ICeeGen::GetSectionCreate-Methode
Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und der Flagwerte.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.  
  
 `flags`  
 [in] Flags, die Optionen angeben.  
  
 `section`  
 [out] Ein Zeiger auf die im Abschnitt neu erstellten Code.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie `GetSectionCreate` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
