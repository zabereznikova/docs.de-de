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
ms.openlocfilehash: a76a7a2d4ad68e367e38e175377aff40ce399346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450207"
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
  
## <a name="members"></a>Mitglieder  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`miCodeTypeMask`|Flags, die den Codetyp beschreiben.|  
|`miIL`|Gibt an, dass die Methoden Implementierung Microsoft Intermediate Language (MSIL) ist.|  
|`miNative`|Gibt an, dass die Methodenimplementierung nativ ist.|  
|`miOPTIL`|Gibt an, dass die Methoden Implementierung OPTIL ist.|  
|`miRuntime`|Gibt an, dass die Methoden Implementierung vom Common Language Runtime bereitgestellt wird.|  
|`miManagedMask`|Flags, die angeben, ob der Code verwaltet oder nicht verwaltet wird.|  
|`miUnmanaged`|Gibt an, dass die Methoden Implementierung nicht verwaltet wird.|  
|`miManaged`|Gibt an, dass die Methoden Implementierung verwaltet wird.|  
|`miForwardRef`|Gibt an, dass die-Methode definiert ist. Dieses Flag wird primär in zusammenlaufverfolgungsszenarios verwendet.|  
|`miPreserveSig`|Gibt an, dass die Methoden Signatur für eine HRESULT-Konvertierung nicht geändert werden kann.|  
|`miInternalCall`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`miSynchronized`|Gibt an, dass die Methode einen Single Thread durch Ihren Text enthält.|  
|`miNoInlining`|Gibt an, dass die Methode nicht intern sein kann.|  
|`miAggressiveInlining`|Gibt an, dass die Methode nach Möglichkeit Inline sein soll.|  
|`miNoOptimization`|Gibt an, dass die Methode nicht optimiert werden soll.|  
|`miMaxMethodImplVal`|Der Höchstwert für einen `CorMethodImpl`.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
