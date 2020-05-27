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
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008329"
---
# <a name="iceegengetsectioncreate-method"></a>ICeeGen::GetSectionCreate-Methode
Generiert einen Code Abschnitt unter Verwendung des angegebenen Namens und der Flagwerte und ruft diesen ab.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 in Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.  
  
 `flags`  
 in Flags, die Optionen angeben.  
  
 `section`  
 vorgenommen Ein Zeiger auf den neu erstellten Code Abschnitt.  
  
## <a name="remarks"></a>Hinweise  
 `GetSectionCreate`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICeeGen-Schnittstelle](iceegen-interface.md)
