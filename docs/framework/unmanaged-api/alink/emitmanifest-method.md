---
title: EmitManifest-Methode
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684940"
---
# <a name="emitmanifest-method"></a>EmitManifest-Methode

Gibt das endgültige Manifest aus. Ruft diese Methode auf, nachdem alle anderen Dateien importiert und alle Optionen festgelegt wurden. Diese Methode darf nicht für ungebundene Module aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 Die ID der Assembly.  
  
 `pdwReserveSize`  
 Empfängt die von der [StrongNameSignatureSize-Funktion](../strong-naming/strongnamesignaturesize-function.md)abgerufene Größe in der Assemblydatei.  
  
 `ptkManifest`  
 Empfängt optional das assemblymanifestoken.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
