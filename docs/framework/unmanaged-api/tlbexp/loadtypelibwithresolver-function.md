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
ms.openlocfilehash: 751794746e26bd8f0ec2cd6db2f62876e78674e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460274"
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver-Funktion
Lädt eine Typbibliothek und verwendet den angegebenen [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) intern referenzierte Typbibliotheken aufgelöst.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szFile`  
 [in] Der Dateipfad der Typbibliothek.  
  
 `regkind`  
 [in] Ein [REGKIND Enumeration](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) Flag, das steuert, wie die Typbibliothek registriert wird. Folgende Werte sind möglich:  
  
-   `REGKIND_DEFAULT`: Verwenden Sie Standardverhalten für die Registrierung.  
  
-   `REGKIND_REGISTER`: Diese Typbibliothek zu registrieren.  
  
-   `REGKIND_NONE`: Diese Typbibliothek keine nicht registriert werden.  
  
 `pTlbResolver`  
 [in] Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Ein Verweis auf die Typbibliothek, die geladen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Werte, die in der folgenden Tabelle aufgeführt.  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|`S_OK`|Erfolgreich.|  
|`E_OUTOFMEMORY`|Nicht genügend Arbeitsspeicher.|  
|`E_POINTER`|Eine oder mehrere der Zeiger sind ungültig.|  
|`E_INVALIDARG`|Eine oder mehrere der Argumente sind ungültig.|  
|`TYPE_E_IOERROR`|Die Funktion konnte nicht in die Datei schreiben.|  
|`TYPE_E_REGISTRYACCESS`|Die Systemdatenbank für die Registrierung konnte nicht geöffnet werden.|  
|`TYPE_E_INVALIDSTATE`|Die Typbibliothek konnte nicht geöffnet werden.|  
|`TYPE_E_CANTLOADLIBRARY`|Die Typbibliothek oder DLL konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) Aufrufe der `LoadTypeLibWithResolver` Funktion während der Konvertierung der Assembly in eine Bibliothek.  
  
 Diese Funktion lädt die angegebene Typbibliothek mit minimalen Zugriff auf die Registrierung. Anschließend überprüft die Funktion die Typbibliothek für Typbibliotheken intern auf die verwiesen wird, von die jede geladen und der übergeordnete Typ-Bibliothek hinzugefügt werden muss.  
  
 Bevor eine referenzierte Typbibliothek geladen werden kann, muss seine Verweispfad für die Datei in einen vollständigen Pfad aufgelöst werden. Dies erfolgt über die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , die vom bereitgestellt der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), der übergeben wird, der `pTlbResolver` Parameter.  
  
 Wenn Sie der vollständigen Dateipfad der Typbibliothek, auf die verwiesen wird, bekannt ist, die `LoadTypeLibWithResolver` Funktion lädt und übergeordneten Typbibliothek, erstellen eine kombinierte master Typbibliothek referenzierten Typbibliothek hinzugefügt.  
  
 Nachdem die Funktion aufgelöst und alle Typbibliotheken intern auf die verwiesen wird lädt, gibt es einen Verweis auf master aufgelöst Typbibliothek in die `pptlib` Parameter.  
  
 Die `LoadTypeLibWithResolver` Funktion wird in der Regel aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), die eigene interne ausgeben [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) Implementierung in der `pTlbResolver` Parameter.  
  
 Beim Aufrufen `LoadTypeLibWithResolver` direkt, geben Sie an Ihre eigenen [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) Implementierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework-Version:** 3.5, 3.0 und 2.0  
  
## <a name="see-also"></a>Siehe auch  
 [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx-Funktion](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)
