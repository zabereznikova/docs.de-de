---
title: CorTypeAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
ms.openlocfilehash: b6936081ca3dbadb4f802a6856fafb53f6cef3fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008962"
---
# <a name="cortypeattr-enumeration"></a>CorTypeAttr-Enumeration
Enthält Werte, die Typmetadaten angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`tdVisibilityMask`|Wird für typsichtbarkeits Informationen verwendet.|  
|`tdNotPublic`|Gibt an, dass der Typ nicht im öffentlichen Gültigkeitsbereich ist.|  
|`tdPublic`|Gibt an, dass der Typ im öffentlichen Gültigkeitsbereich ist.|  
|`tdNestedPublic`|Gibt an, dass der Typ mit öffentlicher Sichtbarkeit eingebettet ist.|  
|`tdNestedPrivate`|Gibt an, dass der Typ mit privater Sichtbarkeit eingebettet ist.|  
|`tdNestedFamily`|Gibt an, dass der Typ mit der Sichtbarkeit der Familie eingebettet ist.|  
|`tdNestedAssembly`|Gibt an, dass der Typ mit der Assemblysichtbarkeit von der Assembly|  
|`tdNestedFamANDAssem`|Gibt an, dass der Typ mit der Sichtbarkeit von Familie und Assembly eingebettet ist.|  
|`tdNestedFamORAssem`|Gibt an, dass der Typ mit der Sichtbarkeit der Familie oder Assembly eingebettet ist.|  
|`tdLayoutMask`|Ruft Layoutinformationen für den Typ ab.|  
|`tdAutoLayout`|Gibt an, dass die Felder dieses Typs automatisch angeordnet werden.|  
|`tdSequentialLayout`|Gibt an, dass die Felder dieses Typs sequenziell angeordnet werden.|  
|`tdExplicitLayout`|Gibt an, dass das Feld Layout explizit angegeben wird.|  
|`tdClassSemanticsMask`|Ruft semantische Informationen über den Typ ab.|  
|`tdClass`|Gibt an, dass der Typ eine Klasse ist.|  
|`tdInterface`|Gibt an, dass der Typ eine Schnittstelle ist.|  
|`tdAbstract`|Gibt an, dass der Typ abstrakt ist.|  
|`tdSealed`|Gibt an, dass der Typ nicht erweitert werden kann.|  
|`tdSpecialName`|Gibt an, dass der Klassenname speziell ist. Der Name beschreibt die Vorgehensweise.|  
|`tdImport`|Gibt an, dass der Typ importiert wird.|  
|`tdSerializable`|Gibt an, dass der Typ serialisierbar ist.|  
|`tdWindowsRuntime`|Gibt an, dass dieser Typ ein Windows-Runtime Typ ist.|  
|`tdStringFormatMask`|Ruft Informationen darüber ab, wie Zeichen folgen codiert und formatiert werden.|  
|`tdAnsiClass`|Gibt an, dass dieser Typ LPTSTR als ANSI interpretiert.|  
|`tdUnicodeClass`|Gibt an, dass dieser Typ LPTSTR als Unicode interpretiert.|  
|`tdAutoClass`|Gibt an, dass dieser Typ LPTSTR automatisch interpretiert.|  
|`tdCustomFormatClass`|Gibt an, dass der Typ über eine nicht standardmäßige Codierung verfügt, wie von angegeben `CustomFormatMask` .|  
|`tdCustomFormatMask`|Verwenden Sie diese Maske, um nicht standardmäßige Codierungsinformationen für systemeigene Interop zu erhalten. Die Bedeutung der Werte dieser beiden Bits ist nicht angegeben.|  
|`tdBeforeFieldInit`|Gibt an, dass der Typ vor dem ersten Versuch, auf ein statisches Feld zuzugreifen, initialisiert werden muss.|  
|`tdForwarder`|Gibt an, dass der Typ exportiert wird, und eine Typweiterleitung.|  
|`tdReservedMask`|Dieses Flag und die folgenden Flags werden intern vom Common Language Runtime verwendet.|  
|`tdRTSpecialName`|Gibt an, dass die Common Language Runtime die namens Codierung überprüfen soll.|  
|`tdHasSecurity`|Gibt an, dass der Typ mit der Sicherheit verknüpft ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
