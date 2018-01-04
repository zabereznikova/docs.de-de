---
title: CorNativeType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeType
helpviewer_keywords: CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6be442dd74f6a71494e140b76357be1bc9e1b747
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cornativetype-enumeration"></a>CorNativeType-Enumeration
Enthält Werte, die systemeigene, nicht verwaltete Typen beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|Veraltet.|  
|`NATIVE_TYPE_VOID`|Veraltet.|  
|`NATIVE_TYPE_BOOLEAN`|Ein boolescher Wert 4-Byte, "true" ungleich 0 (null) und "false steht" ist NULL.|  
|`NATIVE_TYPE_I1`|Eine 8-Bit-Ganzzahl mit Vorzeichen.|  
|`NATIVE_TYPE_U1`|Eine 8-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I2`|Eine 16-Bit-Ganzzahl mit Vorzeichen.|  
|`NATIVE_TYPE_U2`|Eine 16-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I4`|Ein 32-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U4`|Ein 32-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I8`|Eine 64-Bit-Ganzzahl mit Vorzeichen.|  
|`NATIVE_TYPE_U8`|Ein 64-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_R4`|Ein 4-Byte-Gleitkommazahl numerischer Wert.|  
|`NATIVE_TYPE_R8`|Eine 8-Byte-Gleitkommazahl numerischer Wert.|  
|`NATIVE_TYPE_SYSCHAR`|Veraltet.|  
|`NATIVE_TYPE_VARIANT`|Veraltet.|  
|`NATIVE_TYPE_CURRENCY`|Eine numerische COM-Typs, die verwaltete entspricht <xref:System.Decimal> Typ.|  
|`NATIVE_TYPE_PTR`|Veraltet.|  
|`NATIVE_TYPE_DECIMAL`|Veraltet.|  
|`NATIVE_TYPE_DATE`|Veraltet.|  
|`NATIVE_TYPE_BSTR`|COM-Interop.|  
|`NATIVE_TYPE_LPSTR`|Ein Zeichenfolgenwert LPSTR.|  
|`NATIVE_TYPE_LPWSTR`|Ein LPWSTR-Zeichenfolgenwert.|  
|`NATIVE_TYPE_LPTSTR`|Ein Zeichenfolgenwert LPTSTR.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Ein fester, systemdefinierte Zeichenfolgenwert.|  
|`NATIVE_TYPE_OBJECTREF`|Veraltet.|  
|`NATIVE_TYPE_IUNKNOWN`|COM-Interop.|  
|`NATIVE_TYPE_IDISPATCH`|COM-Interop.|  
|`NATIVE_TYPE_STRUCT`|Der Wert einer systemeigenen Struktur.|  
|`NATIVE_TYPE_INTF`|COM-Interop.|  
|`NATIVE_TYPE_SAFEARRAY`|COM-Interop.|  
|`NATIVE_TYPE_FIXEDARRAY`|Ein Wert des Arrays mit fester Länge.|  
|`NATIVE_TYPE_INT`|Eine systemeigene 16-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_UINT`|Eine systemeigene 16-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Veraltet.<br /><br /> Verwenden Sie NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|COM-Interop.|  
|`NATIVE_TYPE_ANSIBSTR`|COM-Interop.|  
|`NATIVE_TYPE_TBSTR`|COM-Interop.<br /><br /> Wählen Sie je nach Plattform BSTR oder ANSIBSTR aus.|  
|`NATIVE_TYPE_VARIANTBOOL`|Ein boolescher 2-Byte-Wert, wobei "true" ist-1 und "false" ist NULL.|  
|`NATIVE_TYPE_FUNC`|Ein Funktionszeiger.|  
|`NATIVE_TYPE_ASANY`|Ein Verweis auf einen beliebigen systemeigenen Typ.|  
|`NATIVE_TYPE_ARRAY`|Ein Verweis auf ein Array mit Elementen eines nicht angegebenen Typs.|  
|`NATIVE_TYPE_LPSTRUCT`|Eine ganze 32-Bit-Zeiger auf eine Struktur.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Einem benutzerdefinierten Marshaller systemeigenen Typ.<br /><br /> Darauf muss durch eine Zeichenfolge im folgenden Format: "systemeigener Typ Name/0Name Marshaller type Name/0Optionaler Cookie/0" oder "{systemeigenen Typ GUID} / 0Name Marshaller type Name/0Optionaler Cookie/0"|  
|`NATIVE_TYPE_ERROR`|COM-Interop.<br /><br /> Mit der ELEMENT_TYPE_I4 wird dieser Typ VT_HRESULT zugeordnet.|  
|`NATIVE_TYPE_IINSPECTABLE`|Ein systemeigenes `IInspectable` Typ.|  
|`NATIVE_TYPE_HSTRING`|Ein systemeigenes `HString`.|  
|`NATIVE_TYPE_MAX`|Ein ungültiger Wert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.UnmanagedType>  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
