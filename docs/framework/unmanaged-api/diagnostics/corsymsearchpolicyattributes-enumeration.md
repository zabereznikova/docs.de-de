---
title: CorSymSearchPolicyAttributes-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178350"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes-Enumeration
Gibt die Richtlinie an, die bei der Suche nach einem Symbolleser verwendet werden soll. Diese Konstanten werden von den [ISymUnmanagedBinder2::GetReaderForFile2-](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) und [ISymUnmanagedBinder3::GetReaderFromCallback-Methoden](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) verwendet.  
  
> [!IMPORTANT]
> Es ist ein Sicherheitsrisiko, eine PDB-Datei (Program Database) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`AllowRegistryAccess`|Fragt die Registrierung nach Symbolsuchpfaden ab.|  
|`AllowSymbolServerAccess`|Greift auf einen Symbolserver zu.|  
|`AllowOriginalPathAccess`|Durchsucht den im Debug-Verzeichnis angegebenen Pfad.|  
|`AllowReferencePathAccess`|Sucht nach der PDB an der Stelle, an der sich die EXE-Datei befindet.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Kopfzeile:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
