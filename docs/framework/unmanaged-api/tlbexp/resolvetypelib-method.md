---
title: ResolveTypeLib-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b430b050117243ced9d764045075071278841da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib-Methode
Löst den einfachen Namen einer Typbibliothek durch den vollqualifizierten Pfad zurückgeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bstrSimpleName`  
 [in] Ein [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , die den einfachen Namen der Typbibliothek enthält.  
  
 `tlbid`  
 [in] Die in der Registrierung der Typbibliothek zugewiesene GUID.  
  
 `lcid`  
 [in] Die Lokalisierungs-ID der Typbibliothek.  
  
 `wMajorVersion`  
 [in] Die Hauptversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.  
  
 `wMinorVersion`  
 [in] Die Nebenversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.  
  
 `syskind`  
 [in] Ein [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) Flag, das die betriebsumgebung identifiziert. Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Ein Zeiger auf eine [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen der `bstrSimpleName` Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Die `ResolveTypeLib` Methode wird aufgerufen, indem Sie die [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) während [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) verarbeiten.  
  
 Benutzerdefinierte Implementierungen dieser Schnittstelle müssen Zurückgeben einer [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen der `bstrSimpleName` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.idl, TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](http://msdn.microsoft.com/en-us/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
