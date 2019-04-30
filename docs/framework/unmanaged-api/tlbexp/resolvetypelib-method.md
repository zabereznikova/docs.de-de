---
title: ResolveTypeLib-Methode
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d734f35b5878ec39e4f2159c326283d168e3be2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040845"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib-Methode
Löst den einfachen Namen einer Typbibliothek durch den vollständig qualifizierten Pfad zurückgeben.  
  
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
  
## <a name="parameters"></a>Parameter  
 `bstrSimpleName`  
 [in] Ein [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , die den einfachen Namen der Typbibliothek enthält.  
  
 `tlbid`  
 [in] Die GUID der Typbibliothek in der Registrierung zugewiesen.  
  
 `lcid`  
 [in] Die Lokalisierungs-ID der Typbibliothek.  
  
 `wMajorVersion`  
 [in] Die Hauptversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.  
  
 `wMinorVersion`  
 [in] Die Nebenversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.  
  
 `syskind`  
 [in] Ein [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) Flag, das die betriebsumgebung identifiziert. Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Ein Zeiger auf eine [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen in der `bstrSimpleName` Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Die `ResolveTypeLib` Methode wird aufgerufen, indem die [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) während [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) verarbeiten.  
  
 Benutzerdefinierte Implementierungen dieser Schnittstelle müssen Zurückgeben einer [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen in der `bstrSimpleName` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.idl, TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
