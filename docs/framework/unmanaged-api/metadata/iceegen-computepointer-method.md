---
title: ICeeGen::ComputePointer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 41a3b9c77fc766b2fa39b406dedbb3203cc97ad9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715471"
---
# <a name="iceegencomputepointer-method"></a>ICeeGen::ComputePointer-Methode

Bestimmt den Puffer für den angegebenen Code Abschnitt.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `section`  
 in Der Code Abschnitt, für den ein Puffer zurückgegeben werden soll.  
  
 `RVA`  
 in Die relative virtuelle Adresse der Methode, für die ein Zeiger erhalten werden soll.  
  
 `lpBuffer`  
 vorgenommen Ein Zeiger auf den zurückgegebenen Puffer.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICeeGen-Schnittstelle](iceegen-interface.md)
