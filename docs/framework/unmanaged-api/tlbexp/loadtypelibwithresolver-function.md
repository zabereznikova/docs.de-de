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
ms.openlocfilehash: b78789344050fd5e1cb0ee3492bf330fbf92bc88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798936"
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver-Funktion
Lädt eine Typbibliothek und verwendet die angegebene [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md) , um alle intern referenzierten Typbibliotheken aufzulösen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Parameter  
 `szFile`  
 in Der Dateipfad der Typbibliothek.  
  
 `regkind`  
 in Ein [REGKIND](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) -Enumerationsflag, das steuert, wie die Typbibliothek registriert wird. Folgende Werte sind möglich:  
  
- `REGKIND_DEFAULT`: Verwenden Sie das Standard Registrierungs Verhalten.  
  
- `REGKIND_REGISTER`: Registrieren Sie diese Typbibliothek.  
  
- `REGKIND_NONE`: Registrieren Sie diese Typbibliothek nicht.  
  
 `pTlbResolver`  
 in Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md).  
  
 `pptlib`  
 vorgenommen Ein Verweis auf die Typbibliothek, die geladen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Werte, der in der folgenden Tabelle aufgeführt ist.  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|`S_OK`|Erfolgreich.|  
|`E_OUTOFMEMORY`|Nicht genügend Arbeitsspeicher.|  
|`E_POINTER`|Mindestens ein Zeiger ist ungültig.|  
|`E_INVALIDARG`|Mindestens eines der Argumente ist ungültig.|  
|`TYPE_E_IOERROR`|Die Funktion konnte nicht in die Datei schreiben.|  
|`TYPE_E_REGISTRYACCESS`|Die System Registrierungsdatenbank konnte nicht geöffnet werden.|  
|`TYPE_E_INVALIDSTATE`|Die Typbibliothek konnte nicht geöffnet werden.|  
|`TYPE_E_CANTLOADLIBRARY`|Die Typbibliothek oder dll konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 " [Tlbexp. exe" (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) ruft `LoadTypeLibWithResolver` die-Funktion während des Konvertierungsprozesses der Assembly in die Typbibliothek auf.  
  
 Diese Funktion lädt die angegebene Typbibliothek mit minimalem Zugriff auf die Registrierung. Die-Funktion untersucht dann die Typbibliothek für intern referenzierte Typbibliotheken, die jeweils geladen und der übergeordneten Typbibliothek hinzugefügt werden müssen.  
  
 Bevor eine Typbibliothek, auf die verwiesen wird, geladen werden kann, muss der Verweis Datei Pfad in einen vollständigen Dateipfad aufgelöst werden. Dies erfolgt über die [ResolveTypeLib-Methode](resolvetypelib-method.md) , die von der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)bereitgestellt wird, die `pTlbResolver` im-Parameter übergeben wird.  
  
 Wenn der vollständige Dateipfad der Typbibliothek, auf die verwiesen `LoadTypeLibWithResolver` wird, bekannt ist, lädt die Funktion die Typbibliothek, auf die verwiesen wird, und fügt Sie der übergeordneten Typbibliothek hinzu  
  
 Nachdem die Funktion alle intern referenzierten Typbibliotheken aufgelöst und geladen hat, gibt Sie einen Verweis auf die vom Master aufgelöste `pptlib` Typbibliothek im-Parameter zurück.  
  
 Die `LoadTypeLibWithResolver` -Funktion wird in der Regel von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen, das im- `pTlbResolver` Parameter eine eigene interne [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung bereitstellt.  
  
 Wenn Sie direkt `LoadTypeLibWithResolver` aufrufen, müssen Sie eine eigene [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Fern** TlbRef.lib  
  
 **.NET Framework Version:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
