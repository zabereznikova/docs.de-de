---
title: IEnumDefinitionIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796473"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity-Schnittstelle
Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` -Objekten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf ein neues `IEnumDefinitionIdentity` -Objekt ab, das dieselben Member wie `IEnumDefinitionIdentity`dieses enthält.|  
|`IEnumDefinitionIdentity::Next`|Ruft die angegebene Anzahl von `IDefinitionIdentity` -Objekten ab der aktuellen Position ab.|  
|`IEnumDefinitionIdentity::Reset`|Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Skip`|Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IDefinitionIdentity-Schnittstelle](idefinitionidentity-interface.md)
