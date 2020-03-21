---
title: CorNativeType-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: 09a351db65c7ed310d3eb68c71a5207ed6040dd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177971"
---
# <a name="cornativetype-enumeration"></a>CorNativeType-Enumeration
Enthält Werte, die systemeigene, nicht verwaltete Typen beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|Veraltet.|  
|`NATIVE_TYPE_VOID`|Veraltet.|  
|`NATIVE_TYPE_BOOLEAN`|Ein boolescher Wert mit 4 Byte, wobei TRUE ungleich Null und FALSE Null ist.|  
|`NATIVE_TYPE_I1`|Ein signierter 8-Bit-Ganzzahlwert.|  
|`NATIVE_TYPE_U1`|Ein nicht signierter 8-Bit-Ganzzahlwert.|  
|`NATIVE_TYPE_I2`|Ein signierter 16-Bit-Ganzzahlwert.|  
|`NATIVE_TYPE_U2`|Ein 16-Bit-Wert mit 16 Bit ohne Vorzeichen.|  
|`NATIVE_TYPE_I4`|Ein 32-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U4`|Ein 32-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I8`|Ein signierter 64-Bit-Ganzzahlwert.|  
|`NATIVE_TYPE_U8`|Ein nicht signierter 64-Bit-Ganzzahlwert.|  
|`NATIVE_TYPE_R4`|Ein numerischer 4-Byte-Gleitkommawert.|  
|`NATIVE_TYPE_R8`|Ein 8-Byte-Gleitkomma-Numerischer Wert.|  
|`NATIVE_TYPE_SYSCHAR`|Veraltet.|  
|`NATIVE_TYPE_VARIANT`|Veraltet.|  
|`NATIVE_TYPE_CURRENCY`|Ein numerischer COM-Typ, <xref:System.Decimal> der dem verwalteten Typ entspricht.|  
|`NATIVE_TYPE_PTR`|Veraltet.|  
|`NATIVE_TYPE_DECIMAL`|Veraltet.|  
|`NATIVE_TYPE_DATE`|Veraltet.|  
|`NATIVE_TYPE_BSTR`|COM-Interop.|  
|`NATIVE_TYPE_LPSTR`|Ein LPSTR-Zeichenfolgenwert.|  
|`NATIVE_TYPE_LPWSTR`|Ein LPWSTR-Zeichenfolgenwert.|  
|`NATIVE_TYPE_LPTSTR`|Ein LPTSTR-Zeichenfolgenwert.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Ein fester, systemdefinierter Zeichenfolgenwert.|  
|`NATIVE_TYPE_OBJECTREF`|Veraltet.|  
|`NATIVE_TYPE_IUNKNOWN`|COM-Interop.|  
|`NATIVE_TYPE_IDISPATCH`|COM-Interop.|  
|`NATIVE_TYPE_STRUCT`|Ein systemeigener Strukturwert.|  
|`NATIVE_TYPE_INTF`|COM-Interop.|  
|`NATIVE_TYPE_SAFEARRAY`|COM-Interop.|  
|`NATIVE_TYPE_FIXEDARRAY`|Ein Arraywert fester Länge.|  
|`NATIVE_TYPE_INT`|Ein systemeigener 16-Bit-signierter Ganzzahlwert.|  
|`NATIVE_TYPE_UINT`|Ein systemeigener 16-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Veraltet.<br /><br /> Verwenden Sie NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|COM-Interop.|  
|`NATIVE_TYPE_ANSIBSTR`|COM-Interop.|  
|`NATIVE_TYPE_TBSTR`|COM-Interop.<br /><br /> Wählen Sie BSTR oder ANSIBSTR je nach Plattform.|  
|`NATIVE_TYPE_VARIANTBOOL`|Ein boolescher Wert mit 2 Byte, wobei TRUE -1 und FALSE Null ist.|  
|`NATIVE_TYPE_FUNC`|Ein Funktionszeiger.|  
|`NATIVE_TYPE_ASANY`|Ein Verweis auf jeden systemeigenen Typ.|  
|`NATIVE_TYPE_ARRAY`|Ein Verweis auf ein Array mit Membern eines nicht angegebenen Typs.|  
|`NATIVE_TYPE_LPSTRUCT`|Ein 32-Bit-Ganzzahlzeiger auf eine Struktur.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Ein benutzerdefinierter, systemeigener Marshallertyp.<br /><br /> Darauf muss eine Zeichenfolge des folgenden Formats folgen: "Native type name/0Custom marshaler type name/0Optional cookie/0" oder "'Native type GUID'/0Custom marshaler type name/0Optional cookie/0"|  
|`NATIVE_TYPE_ERROR`|COM-Interop.<br /><br /> Mit ELEMENT_TYPE_I4 dieser Typ karten VT_HRESULT.|  
|`NATIVE_TYPE_IINSPECTABLE`|Ein `IInspectable` systemeigener Typ.|  
|`NATIVE_TYPE_HSTRING`|Ein `HString`einheimischer .|  
|`NATIVE_TYPE_MAX`|Ein ungültiger Wert.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
