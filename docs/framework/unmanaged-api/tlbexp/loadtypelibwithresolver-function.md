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
ms.openlocfilehash: adbb5eca3b7ffa36d0c963d0dacc3b2afdb664d4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935564"
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
  
## <a name="parameters"></a>Parameters  
 `szFile`  
 in Der Dateipfad der Typbibliothek.  
  
 `regkind`  
 in Ein [REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) -Enumerationsflag, das steuert, wie die Typbibliothek registriert wird. Folgende Werte sind möglich:  
  
- `REGKIND_DEFAULT`: Verwenden Sie das Standard Registrierungs Verhalten.  
  
- `REGKIND_REGISTER`: diese Typbibliothek registrieren.  
  
- `REGKIND_NONE`: diese Typbibliothek nicht registrieren.  
  
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
|`E_INVALIDARG`|Mindestens ein Argument ist ungültig.|  
|`TYPE_E_IOERROR`|Die Funktion konnte nicht in die Datei schreiben.|  
|`TYPE_E_REGISTRYACCESS`|Die System Registrierungsdatenbank konnte nicht geöffnet werden.|  
|`TYPE_E_INVALIDSTATE`|Die Typbibliothek konnte nicht geöffnet werden.|  
|`TYPE_E_CANTLOADLIBRARY`|Die Typbibliothek oder dll konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 " [Tlbexp. exe" (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) Ruft die `LoadTypeLibWithResolver`-Funktion während des Konvertierungsprozesses der Assembly in eine Typbibliothek auf.  
  
 Diese Funktion lädt die angegebene Typbibliothek mit minimalem Zugriff auf die Registrierung. Die-Funktion untersucht dann die Typbibliothek für intern referenzierte Typbibliotheken, die jeweils geladen und der übergeordneten Typbibliothek hinzugefügt werden müssen.  
  
 Bevor eine Typbibliothek, auf die verwiesen wird, geladen werden kann, muss der Verweis Datei Pfad in einen vollständigen Dateipfad aufgelöst werden. Dies erfolgt über die [ResolveTypeLib-Methode](resolvetypelib-method.md) , die von der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)bereitgestellt wird, die im `pTlbResolver`-Parameter übergeben wird.  
  
 Wenn der vollständige Dateipfad der Typbibliothek, auf die verwiesen wird, bekannt ist, lädt die `LoadTypeLibWithResolver` Funktion die Typbibliothek, auf die verwiesen wird, und fügt Sie der übergeordneten Typbibliothek hinzu  
  
 Nachdem die Funktion alle intern referenzierten Typbibliotheken aufgelöst und geladen hat, gibt Sie einen Verweis auf die vom Master aufgelöste Typbibliothek im `pptlib`-Parameter zurück.  
  
 Die `LoadTypeLibWithResolver`-Funktion wird in der Regel von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen, das eine eigene interne [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung im Parameter `pTlbResolver` bereitstellt.  
  
 Wenn Sie `LoadTypeLibWithResolver` direkt aufrufen, müssen Sie eine eigene [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung angeben.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** TlbRef. h  
  
 **Bibliothek:** TlbRef. lib  
  
 **.NET Framework Version:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
