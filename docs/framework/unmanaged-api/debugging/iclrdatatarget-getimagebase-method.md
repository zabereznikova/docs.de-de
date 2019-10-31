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
ms.openlocfilehash: fed643ae52f50b1b8cd134880c644c8941da6f56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122874"
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
 vorgenommen Ein Zeiger auf ein CLRDATA_ADDRESS, in dem die Basisadresse des Bilds gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Bild Dateiname darf keinen Pfad aufweisen. Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
