---
title: CorMethodImpl-Enumeration
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c88c12646a13e5a24f2475bd2db04c8c831141c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781765"
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl-Enumeration
Enthält Werte, die Funktionen zur Implementierung von Methoden beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`miCodeTypeMask`|Flags, die Codetyp beschreiben.|  
|`miIL`|Gibt an, dass die methodenimplementierung Microsoft intermediate Language (MSIL).|  
|`miNative`|Gibt an, dass die Methodenimplementierung nativ ist.|  
|`miOPTIL`|Gibt an, dass die methodenimplementierung OPTIL.|  
|`miRuntime`|Gibt an, dass die methodenimplementierung von der common Language Runtime bereitgestellt wird.|  
|`miManagedMask`|Flags, die angibt, ob der Code verwaltet oder nicht verwaltet wird.|  
|`miUnmanaged`|Gibt an, dass die methodenimplementierung nicht verwaltet ist.|  
|`miManaged`|Gibt an, dass die methodenimplementierung verwaltet wird.|  
|`miForwardRef`|Gibt an, dass die Methode definiert ist. Dieses Flag wird in erster Linie in der Merge-Szenarien verwendet.|  
|`miPreserveSig`|Gibt an, dass die Signatur der Methode für eine Konvertierung von HRESULT nicht geändert werden kann.|  
|`miInternalCall`|Durch die common Language Runtime können Sie für die interne Verwendung reserviert.|  
|`miSynchronized`|Gibt an, dass die Methode mit Textkörpers Single-Thread.|  
|`miNoInlining`|Gibt an, dass die Methode nicht intern sein kann.|  
|`miAggressiveInlining`|Gibt an, dass die Methode nach Möglichkeit intern sein sollte.|  
|`miNoOptimization`|Gibt an, dass die Methode nicht optimiert werden soll.|  
|`miMaxMethodImplVal`|Der gültige Höchstwert für eine `CorMethodImpl`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
