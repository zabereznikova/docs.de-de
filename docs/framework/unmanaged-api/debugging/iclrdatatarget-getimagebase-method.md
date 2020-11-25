---
title: ICLRDataTarget::GetImageBase-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703576"
---
# <a name="iclrdatatargetgetimagebase-method"></a>ICLRDataTarget::GetImageBase-Methode

Ruft die Basis Speicheradresse des angegebenen Bilds ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `imagePath`  
 in Der Dateiname des Bilds, einschließlich des Pfads.  
  
 `baseAddress`  
 vorgenommen Ein Zeiger auf einen CLRDATA_ADDRESS, der die Basisadresse des Bilds speichert.  
  
## <a name="remarks"></a>Hinweise  

 Der Bild Dateiname darf keinen Pfad aufweisen. Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
