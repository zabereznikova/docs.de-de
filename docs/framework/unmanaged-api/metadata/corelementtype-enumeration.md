---
title: CorElementType-Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5112c3c8d5fef6efada4bffdfa575716503515e6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041355"
---
# <a name="corelementtype-enumeration1"></a>CorElementType-Enumeration1
Gibt an, eine common Language Runtime <xref:System.Type>, einen Typmodifizierer oder Informationen zu einem Typ in einer Signatur der Metadaten-Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|Wird intern verwendet.|  
|`ELEMENT_TYPE_VOID`|Ein void-Typ.|  
|`ELEMENT_TYPE_BOOLEAN`|Ein boolescher Typ|  
|`ELEMENT_TYPE_CHAR`|Ein Zeichentyp.|  
|`ELEMENT_TYPE_I1`|Eine 1-Byte-Ganzzahl.|  
|`ELEMENT_TYPE_U1`|Ein unsignierter 1-Byte-Ganzzahltyp.|  
|`ELEMENT_TYPE_I2`|Eine 2-Byte-Ganzzahl.|  
|`ELEMENT_TYPE_U2`|Eine 2-Byte-Ganzzahl ohne Vorzeichen.|  
|`ELEMENT_TYPE_I4`|Eine 4-Byte-Ganzzahl.|  
|`ELEMENT_TYPE_U4`|Eine 4-Byte-Ganzzahl ohne Vorzeichen.|  
|`ELEMENT_TYPE_I8`|Eine 8-Byte-Ganzzahl.|  
|`ELEMENT_TYPE_U8`|Eine 8-Byte-Ganzzahl ohne Vorzeichen.|  
|`ELEMENT_TYPE_R4`|Eine 4-Byte-Gleitkommazahl.|  
|`ELEMENT_TYPE_R8`|Eine 8-Byte-Gleitkommazahl.|  
|`ELEMENT_TYPE_STRING`|Ein System.String-Typ.|  
|`ELEMENT_TYPE_PTR`|Ein Typmodifizierer "Zeiger".|  
|`ELEMENT_TYPE_BYREF`|Ein Modifizierer für den Verweis-Typ.|  
|`ELEMENT_TYPE_VALUETYPE`|Typmodifizierer Wert.|  
|`ELEMENT_TYPE_CLASS`|Ein Typmodifizierer "Klasse".|  
|`ELEMENT_TYPE_VAR`|Ein Variablentyp Modifizierer der Klasse.|  
|`ELEMENT_TYPE_ARRAY`|Ein mehrdimensionales Array-Typ-Modifizierer.|  
|`ELEMENT_TYPE_GENERICINST`|Ein Typmodifizierer für generische Typen.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Ein typisierter Verweis.|  
|`ELEMENT_TYPE_I`|Die Größe des eine systemeigene ganze Zahl.|  
|`ELEMENT_TYPE_U`|Die Größe des systemeigenen Ganzzahl ohne Vorzeichen.|  
|`ELEMENT_TYPE_FNPTR`|Ein Zeiger auf eine Funktion.|  
|`ELEMENT_TYPE_OBJECT`|Ein System.Object-Typ.|  
|`ELEMENT_TYPE_SZARRAY`|Ein eindimensionales, NULL Typmodifizierer Untergrenze Array.|  
|`ELEMENT_TYPE_MVAR`|Methodenmodifizierer Variablentyp.|  
|`ELEMENT_TYPE_CMOD_REQD`|Eine C#-Sprache erforderlich Modifizierer.|  
|`ELEMENT_TYPE_CMOD_OPT`|Eine C#-Sprache Optionaler Modifizierer.|  
|`ELEMENT_TYPE_INTERNAL`|Wird intern verwendet.|  
|`ELEMENT_TYPE_MAX`|Ein ungültiger Typ.|  
|`ELEMENT_TYPE_MODIFIER`|Wird intern verwendet.|  
|`ELEMENT_TYPE_SENTINEL`|Ein Typmodifizierer, der eine Liste der eine Variable Anzahl von Parametern Sentinel ist.|  
|`ELEMENT_TYPE_PINNED`|Wird intern verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Der Typmodifizierer bilden die Grundlage für komplexere Typen darstellt. Ein `CorElementType` Typwert-Modifizierer wird angewendet, auf den Wert, der durch den sie in der Typsignatur unmittelbar folgt. Der Wert, der `CorElementType` Modifizierer Typwert möglich ein `CorElementType` einfacher Werttyp, ein Metadatentoken, oder ein anderer Wert als in der folgenden Tabelle angegeben.  
  
> [!NOTE]
>  Alle Zahlen (*Anzahl*, *Argumentanzahl*, *Metadatentoken*, *Rang*, *Anzahl*, und *gebunden*) als komprimierte ganze Zahlen gespeichert werden. Finden Sie unter [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) auf der ECMA-Website für Details.  
  
|Typmodifizierer|Format|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < eine `CorElementType` Wert >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < eine `CorElementType` Wert >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < ein `mdTypeDef` Metadatentoken >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < ein `mdTypeDef` Metadatentoken >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<Anzahl >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < eine `CorElementType` Wert > \<Rang > \<count1 > \<bound1 >... \<CountN > \<BoundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < ein `mdTypeDef` Metadatentoken > \<Argumentanzahl > \<arg1 >... \<ArgN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<vollständige Signatur für die Funktion, einschließlich der Aufrufkonvention >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < eine `CorElementType` Wert >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<Anzahl >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < eine `mdTypeRef` oder `mdTypeDef` Metadatentoken >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < eine `mdTypeRef` oder `mdTypeDef` Metadatentoken >|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
