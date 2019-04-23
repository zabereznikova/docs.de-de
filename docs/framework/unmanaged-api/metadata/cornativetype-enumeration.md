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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf62000fd4ec5c8f3dea3fa7d560b3f9ead33fa7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113918"
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
|`NATIVE_TYPE_BOOLEAN`|Ein 4-Byte-boolescher Wert, wobei "true" nicht 0 (null) und "false" ist, wird 0 (null).|  
|`NATIVE_TYPE_I1`|Eine 8-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U1`|Eine 8-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I2`|Eine 16-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U2`|Eine 16-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I4`|Ein 32-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U4`|Ein 32-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_I8`|Eine 64-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_U8`|Eine 64-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_R4`|Ein 4-Byte-Gleitkommazahl numerischer Wert.|  
|`NATIVE_TYPE_R8`|Eine 8-Byte-Gleitkommazahl numerischer Wert.|  
|`NATIVE_TYPE_SYSCHAR`|Veraltet.|  
|`NATIVE_TYPE_VARIANT`|Veraltet.|  
|`NATIVE_TYPE_CURRENCY`|Ein numerischer COM-Typ, der die verwaltete entspricht <xref:System.Decimal> Typ.|  
|`NATIVE_TYPE_PTR`|Veraltet.|  
|`NATIVE_TYPE_DECIMAL`|Veraltet.|  
|`NATIVE_TYPE_DATE`|Veraltet.|  
|`NATIVE_TYPE_BSTR`|COM-Interop.|  
|`NATIVE_TYPE_LPSTR`|Ein Zeichenfolgenwert des LPSTR.|  
|`NATIVE_TYPE_LPWSTR`|Ein Zeichenfolgenwert des LPWSTR.|  
|`NATIVE_TYPE_LPTSTR`|Ein Zeichenfolgenwert des LPTSTR.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Ein fester, vom System definierten Zeichenfolgenwert.|  
|`NATIVE_TYPE_OBJECTREF`|Veraltet.|  
|`NATIVE_TYPE_IUNKNOWN`|COM-Interop.|  
|`NATIVE_TYPE_IDISPATCH`|COM-Interop.|  
|`NATIVE_TYPE_STRUCT`|Der Wert einer systemeigenen Struktur.|  
|`NATIVE_TYPE_INTF`|COM-Interop.|  
|`NATIVE_TYPE_SAFEARRAY`|COM-Interop.|  
|`NATIVE_TYPE_FIXEDARRAY`|Ein Array fester Länge-Wert.|  
|`NATIVE_TYPE_INT`|Eine native 16-Bit-Ganzzahlwert mit Vorzeichen.|  
|`NATIVE_TYPE_UINT`|Eine native 16-Bit-Ganzzahlwert ohne Vorzeichen.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Veraltet.<br /><br /> Verwenden Sie NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|COM-Interop.|  
|`NATIVE_TYPE_ANSIBSTR`|COM-Interop.|  
|`NATIVE_TYPE_TBSTR`|COM-Interop.<br /><br /> Wählen Sie BSTR oder ANSIBSTR, abhängig von der Plattform.|  
|`NATIVE_TYPE_VARIANTBOOL`|Ein boolescher 2-Byte-Wert, wobei "true" ist-1 und "false" ist 0 (null).|  
|`NATIVE_TYPE_FUNC`|Ein Funktionszeiger.|  
|`NATIVE_TYPE_ASANY`|Ein Verweis auf einen beliebigen systemeigenen Typ.|  
|`NATIVE_TYPE_ARRAY`|Ein Verweis auf ein Array mit Elementen eines nicht angegebenen Typs.|  
|`NATIVE_TYPE_LPSTRUCT`|Eine ganze 32-Bit-Zeiger auf eine Struktur.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Ein systemeigener Typ des benutzerdefinierten Marshallers.<br /><br /> Dies muss eine Zeichenfolge im folgenden Format folgen: "Systemeigener Typ Name/0Name Marshaller type/0Optionaler Cookie/0" oder "{Native geben GUID} / 0Name Marshaller type/0Optionaler Cookie/0"|  
|`NATIVE_TYPE_ERROR`|COM-Interop.<br /><br /> Ordnet diesen Typ mit ELEMENT_TYPE_I4 VT_HRESULT zugeordnet.|  
|`NATIVE_TYPE_IINSPECTABLE`|Ein systemeigenes `IInspectable` Typ.|  
|`NATIVE_TYPE_HSTRING`|Ein systemeigenes `HString`.|  
|`NATIVE_TYPE_MAX`|Ein ungültiger Wert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
