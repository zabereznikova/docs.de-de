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
ms.openlocfilehash: 6497dd3e720874e47de9dfda74e483a642cbb181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708230"
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
 in Ein [REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) -Enumerationsflag, das steuert, wie die Typbibliothek registriert wird. Folgende Werte sind möglich:  
  
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
|`S_OK`|Erfolg.|  
|`E_OUTOFMEMORY`|Nicht genügend Arbeitsspeicher.|  
|`E_POINTER`|Mindestens ein Zeiger ist ungültig.|  
|`E_INVALIDARG`|Mindestens ein Argument ist ungültig.|  
|`TYPE_E_IOERROR`|Die Funktion konnte nicht in die Datei schreiben.|  
|`TYPE_E_REGISTRYACCESS`|Die System Registrierungsdatenbank konnte nicht geöffnet werden.|  
|`TYPE_E_INVALIDSTATE`|Die Typbibliothek konnte nicht geöffnet werden.|  
|`TYPE_E_CANTLOADLIBRARY`|Die Typbibliothek oder dll konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  

 Der [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) Ruft die- `LoadTypeLibWithResolver` Funktion während des Konvertierungsprozesses der Assembly in die Typbibliothek auf.  
  
 Diese Funktion lädt die angegebene Typbibliothek mit minimalem Zugriff auf die Registrierung. Die-Funktion untersucht dann die Typbibliothek für intern referenzierte Typbibliotheken, die jeweils geladen und der übergeordneten Typbibliothek hinzugefügt werden müssen.  
  
 Bevor eine Typbibliothek, auf die verwiesen wird, geladen werden kann, muss der Verweis Datei Pfad in einen vollständigen Dateipfad aufgelöst werden. Dies erfolgt über die [ResolveTypeLib-Methode](resolvetypelib-method.md) , die von der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)bereitgestellt wird, die im-Parameter übergeben wird `pTlbResolver` .  
  
 Wenn der vollständige Dateipfad der Typbibliothek, auf die verwiesen wird, bekannt ist, `LoadTypeLibWithResolver` lädt die Funktion die Typbibliothek, auf die verwiesen wird, und fügt Sie der übergeordneten Typbibliothek hinzu  
  
 Nachdem die Funktion alle intern referenzierten Typbibliotheken aufgelöst und geladen hat, gibt Sie einen Verweis auf die vom Master aufgelöste Typbibliothek im- `pptlib` Parameter zurück.  
  
 Die- `LoadTypeLibWithResolver` Funktion wird in der Regel von der [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen, die im-Parameter eine eigene interne [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung bereitstellt `pTlbResolver` .  
  
 Wenn Sie `LoadTypeLibWithResolver` direkt aufrufen, müssen Sie eine eigene [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung angeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** TlbRef. h  
  
 **Bibliothek:** TlbRef. lib  
  
 **.NET Framework Version:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>Weitere Informationen

- [Tlbexp-Hilfsfunktionen](index.md)
- [LoadTypeLibEx-Funktion](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
