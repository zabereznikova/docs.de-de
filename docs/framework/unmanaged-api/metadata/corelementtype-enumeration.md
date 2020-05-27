---
title: CorElementType-Enumeration
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
ms.openlocfilehash: 25fb3278e576ebe4a538379918e868b2e5f87911
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007870"
---
# <a name="corelementtype-enumeration"></a>CorElementType-Enumeration

Gibt eine Common Language Runtime <xref:System.Type> , einen Typmodifizierer oder Informationen zu einem Typ in einer Signatur des metadatentyps an.

## <a name="syntax"></a>Syntax

```cpp
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
|`ELEMENT_TYPE_I1`|Eine ganze 1-Byte-Ganzzahl mit Vorzeichen.|
|`ELEMENT_TYPE_U1`|Ein unsignierter 1-Byte-Ganzzahltyp.|
|`ELEMENT_TYPE_I2`|Eine ganze 2-Byte-Ganzzahl mit Vorzeichen.|
|`ELEMENT_TYPE_U2`|Eine 2-Byte-Ganzzahl ohne Vorzeichen.|
|`ELEMENT_TYPE_I4`|Eine ganze 4-Byte-Ganzzahl mit Vorzeichen.|
|`ELEMENT_TYPE_U4`|Eine ganze 4-Byte-Ganzzahl ohne Vorzeichen.|
|`ELEMENT_TYPE_I8`|Eine 8-Byte-Ganzzahl mit Vorzeichen.|
|`ELEMENT_TYPE_U8`|Eine 8-Byte-Ganzzahl ohne Vorzeichen.|
|`ELEMENT_TYPE_R4`|Ein 4-Byte-Gleit Komma Wert.|
|`ELEMENT_TYPE_R8`|Ein 8-Byte-Gleit Komma Wert.|
|`ELEMENT_TYPE_STRING`|Ein System. String-Typ.|
|`ELEMENT_TYPE_PTR`|Ein zeigertypmodifizierer.|
|`ELEMENT_TYPE_BYREF`|Ein Verweistyp Modifizierer.|
|`ELEMENT_TYPE_VALUETYPE`|Ein Werttyp-Modifizierer.|
|`ELEMENT_TYPE_CLASS`|Ein Klassentyp Modifizierer.|
|`ELEMENT_TYPE_VAR`|Ein Klassen variablentypmodifizierer.|
|`ELEMENT_TYPE_ARRAY`|Ein mehrdimensionaler Arraytypmodifizierer.|
|`ELEMENT_TYPE_GENERICINST`|Ein Typmodifizierer für generische Typen.|
|`ELEMENT_TYPE_TYPEDBYREF`|Ein typisierter Verweis.|
|`ELEMENT_TYPE_I`|Größe einer nativen Ganzzahl.|
|`ELEMENT_TYPE_U`|Größe einer nativen Ganzzahl ohne Vorzeichen.|
|`ELEMENT_TYPE_FNPTR`|Ein Zeiger auf eine Funktion.|
|`ELEMENT_TYPE_OBJECT`|Ein System. Object-Typ.|
|`ELEMENT_TYPE_SZARRAY`|Ein eindimensionaler Arraytypmodifizierer (null).|
|`ELEMENT_TYPE_MVAR`|Ein Typmodifizierer für die-Methode.|
|`ELEMENT_TYPE_CMOD_REQD`|Ein Modifizierer der C-Sprache erforderlich.|
|`ELEMENT_TYPE_CMOD_OPT`|Ein optionaler C-sprach Modifizierer.|
|`ELEMENT_TYPE_INTERNAL`|Wird intern verwendet.|
|`ELEMENT_TYPE_MAX`|Ein ungültiger Typ.|
|`ELEMENT_TYPE_MODIFIER`|Wird intern verwendet.|
|`ELEMENT_TYPE_SENTINEL`|Ein Typmodifizierer, bei dem es sich um einen Sentinel für eine Liste mit einer Variablen Anzahl von Parametern handelt.|
|`ELEMENT_TYPE_PINNED`|Wird intern verwendet.|

## <a name="remarks"></a>Hinweise

Die typmodifiziererer bilden die Grundlage für das darstellen komplexer Typen. Ein `CorElementType` Typmodifiziererwert wird auf den Wert angewendet, der in der Typsignatur unmittelbar darauf folgt. Der Wert, der `CorElementType` auf den Typmodifiziererwert folgt, kann ein `CorElementType` einfacher Typwert, ein Metadatentoken oder ein anderer Wert sein, wie in der folgenden Tabelle angegeben.

> [!NOTE]
> Alle Zahlen (*Anzahl*, *Argument Anzahl*, *metadata token*Metadatentoken, *Rang*, *Anzahl*und *gebunden*) werden als komprimierte ganze Zahlen gespeichert. Weitere Informationen finden Sie in der ECMA [-Website Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) .

|Typmodifizierer|Format|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR\<a `CorElementType` value>|
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF\<a `CorElementType` value>|
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR\<number>|
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN>\<boundN>|
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ...\<argN>|
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR\<complete signature for the function, including calling convention>|
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY\<a `CorElementType` value>|
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR\<number>|
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT\<a `mdTypeRef` or `mdTypeDef` metadata token>|

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Corhdr. h

**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
