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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43e7c973ee22350f26b4f86bcc8b4c4c727291ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087286"
---
# <a name="cortypeattr-enumeration"></a>CorTypeAttr-Enumeration
Enthält Werte, die Typmetadaten angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`tdVisibilityMask`|Für Informationen zur Sichtbarkeit des Typs verwendet.|  
|`tdNotPublic`|Gibt an, dass der Typ nicht im öffentlichen Bereich ist.|  
|`tdPublic`|Gibt an, dass der Typ im öffentlichen Bereich.|  
|`tdNestedPublic`|Gibt an, dass der Typ mit öffentlicher Sichtbarkeit geschachtelt ist.|  
|`tdNestedPrivate`|Gibt an, dass der Typ mit privater Sichtbarkeit geschachtelt ist.|  
|`tdNestedFamily`|Gibt an, dass der Typ mit familiensichtbarkeit geschachtelt ist.|  
|`tdNestedAssembly`|Gibt an, dass der Typ mit Assemblysichtbarkeit geschachtelt ist.|  
|`tdNestedFamANDAssem`|Gibt an, dass der Typ mit Familien- und Assemblysichtbarkeit geschachtelt ist.|  
|`tdNestedFamORAssem`|Gibt an, dass der Typ mit Familien- oder Assemblysichtbarkeit geschachtelt ist.|  
|`tdLayoutMask`|Ruft Layoutinformationen für den Typ ab.|  
|`tdAutoLayout`|Gibt an, dass die Felder dieses Typs automatisch angeordnet werden.|  
|`tdSequentialLayout`|Gibt an, dass die Felder dieses Typs sequenziell angelegt werden.|  
|`tdExplicitLayout`|Gibt an, dass das Feldlayout explizit bereitgestellt wird.|  
|`tdClassSemanticsMask`|Ruft die semantischen Informationen über den Typ ab.|  
|`tdClass`|Gibt an, dass der Typ eine Klasse ist.|  
|`tdInterface`|Gibt an, dass der Typ eine Schnittstelle ist.|  
|`tdAbstract`|Gibt an, dass der Typ abstrakt ist.|  
|`tdSealed`|Gibt an, dass der Typ nicht erweitert werden kann.|  
|`tdSpecialName`|Gibt an, dass der Klassenname spezielle. Der Name wird beschrieben, wie.|  
|`tdImport`|Gibt an, dass der Typ importiert wird.|  
|`tdSerializable`|Gibt an, dass der Typ serialisierbar ist.|  
|`tdWindowsRuntime`|Gibt an, dass dieser Typ ist ein [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typ.|  
|`tdStringFormatMask`|Ruft Informationen über die Zeichenfolgen codiert und formatiert werden.|  
|`tdAnsiClass`|Gibt an, dass dieser Typ eine LPTSTR als ANSI interpretiert.|  
|`tdUnicodeClass`|Gibt an, dass dieser Typ eine LPTSTR als Unicode interpretiert.|  
|`tdAutoClass`|Gibt an, dass dieser Typ eine LPTSTR automatisch interpretiert.|  
|`tdCustomFormatClass`|Gibt an, dass der Typ einer nicht standardmäßigen Codierung gemäß `CustomFormatMask`.|  
|`tdCustomFormatMask`|Verwenden Sie diese Maske, um nicht standardkonforme Codierungsinformationen für systemeigenes Interop abzurufen. Die Bedeutung der Werte der diese zwei Bits ist nicht angegeben.|  
|`tdBeforeFieldInit`|Gibt an, dass der Typ muss, bevor beim ersten Versuch initialisiert werden, ein statisches Feld zugreifen.|  
|`tdForwarder`|Gibt an, dass der Typ exportiert wird, und eine typweiterleitung.|  
|`tdReservedMask`|Dieses Flag und die folgenden Flags werden intern von der common Language Runtime verwendet.|  
|`tdRTSpecialName`|Gibt an, dass die common Language Runtime die namenscodierung überprüfen soll.|  
|`tdHasSecurity`|Gibt an, dass der Typ Sicherheit zugeordnet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
