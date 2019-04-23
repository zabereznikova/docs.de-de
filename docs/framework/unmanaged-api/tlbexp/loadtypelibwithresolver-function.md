---
title: LoadTypeLibWithResolver-Funktion
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c14080e3ac128a6a7fbb48586f59d8a5ea4105f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155655"
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver-Funktion
Lädt eine Typbibliothek und verwendet die angegebene [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) intern referenzierte Typbibliotheken aufgelöst.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Parameter  
 `szFile`  
 [in] Der Dateipfad der Typbibliothek.  
  
 `regkind`  
 [in] Ein [REGKIND Enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) Flag, das steuert, wie die Typbibliothek registriert wird. Die Werte sind möglich:  
  
-   `REGKIND_DEFAULT`: Verwenden Sie Standardverhalten für die Registrierung.  
  
-   `REGKIND_REGISTER`: Diese Typbibliothek zu registrieren.  
  
-   `REGKIND_NONE`: Führen Sie diese Typbibliothek nicht registriert werden.  
  
 `pTlbResolver`  
 [in] Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Ein Verweis auf die Typbibliothek, die geladen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Einer der in der folgenden Tabelle aufgeführten HRESULT-Werte.  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|`S_OK`|Erfolgreich.|  
|`E_OUTOFMEMORY`|Nicht genügend Arbeitsspeicher.|  
|`E_POINTER`|Eine oder mehrere der Zeiger sind ungültig.|  
|`E_INVALIDARG`|Eine oder mehrere der Argumente sind ungültig.|  
|`TYPE_E_IOERROR`|Die Funktion konnte nicht in die Datei schreiben.|  
|`TYPE_E_REGISTRYACCESS`|Die Systemdatenbank für die Registrierung konnte nicht geöffnet werden.|  
|`TYPE_E_INVALIDSTATE`|Die Typbibliothek konnte nicht geöffnet werden.|  
|`TYPE_E_CANTLOADLIBRARY`|Die Typbibliothek oder einer DLL konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) Aufrufe der `LoadTypeLibWithResolver` Funktion während der Konvertierung der Assembly in den Typ in der Bibliothek.  
  
 Diese Funktion lädt die angegebene Typbibliothek mit minimalen Zugriff auf die Registrierung. Die Funktion überprüft dann die Typbibliothek für Typbibliotheken intern auf die verwiesen wird, von die jede geladen und der übergeordnete Typ-Bibliothek hinzugefügt werden muss.  
  
 Bevor eine referenzierte Typbibliothek geladen werden kann, muss die Verweis-Dateipfad in einen vollständigen Dateipfad aufgelöst werden. Dies erfolgt über die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , erfolgt über die [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), im übergeben wird die `pTlbResolver` Parameter.  
  
 Wenn Sie der vollständigen Pfad der Typbibliothek, auf die verwiesen wird, bekannt ist, die `LoadTypeLibWithResolver` Funktion lädt und die Bibliothek mit übergeordneten, erstellen eine kombinierte master Typbibliothek die referenzierte Bibliothek hinzugefügt.  
  
 Nachdem die Funktion aufgelöst und alle intern Typbibliotheken lädt, gibt es einen Verweis auf master aufgelöst Typbibliothek in der `pptlib` Parameter.  
  
 Die `LoadTypeLibWithResolver` Funktion ist in der Regel aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), die stellt eine eigene, interne [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) -Implementierung in der `pTlbResolver` der Parameter.  
  
 Wenn Sie aufrufen `LoadTypeLibWithResolver` direkt, geben Sie an Ihre eigenen [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) Implementierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework Version:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
