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
ms.openlocfilehash: 0f274befe78e45be3e53335572fd9c1e0b401fd3
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040172"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib-Methode
Löst den einfachen Namen einer Typbibliothek auf, indem der voll qualifizierte Pfad zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , das den einfachen Namen der Typbibliothek enthält.  
  
 `tlbid`  
 in Die GUID, die der Typbibliothek in der Registrierung zugewiesen ist.  
  
 `lcid`  
 in Die Lokalisierungs-ID der Typbibliothek.  
  
 `wMajorVersion`  
 in Die Hauptversionsnummer der Typbibliothek. Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.  
  
 `wMinorVersion`  
 in Die neben Versionsnummer der Typbibliothek. Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.  
  
 `syskind`  
 in Ein [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das die Betriebsumgebung identifiziert. Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 vorgenommen Ein Zeiger auf einen [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) -Wert, der den vollständigen Pfad der Typbibliothek mit `bstrSimpleName` dem Namen im-Parameter enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `ResolveTypeLib` -Methode wird von der [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) während der Verarbeitung von [Tlbexp. exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) aufgerufen.  
  
 Benutzerdefinierte Implementierungen dieser Schnittstelle müssen einen [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) -Wert zurückgeben, der den vollständigen Pfad der Typbibliothek mit dem Namen im `bstrSimpleName` -Parameter enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.idl, TlbRef.h  
  
 **Fern** TlbRef.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
