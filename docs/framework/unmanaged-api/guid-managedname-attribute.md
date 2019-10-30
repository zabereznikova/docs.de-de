---
title: GUID_ManagedName-Attribut
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
ms.openlocfilehash: 9d30c8fe71a0dfff7de9bb2f43b325cbb8016a23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123038"
---
# <a name="guid_managedname-attribute"></a>GUID_ManagedName-Attribut
Definiert ein benutzerdefiniertes Schnittstellen Attribut, das den Namen des verwalteten Namespace für eine COM-Bibliothek (Component Object Model) angibt.  
  
## <a name="syntax"></a>Syntax  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parameter  
 `value`  
 Der verwaltete Namespace Name für die Bibliothek.  
  
## <a name="definition"></a>Definition  
 `GUID_ManagedName` ist in Cor. h wie folgt definiert:  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein benutzerdefiniertes Schnittstellen Attribut definiert Metadaten für ein Objekt in der Typbibliothek.  
  
 Verwenden Sie <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>, um den verwalteten Namen aus dem-Attribut abzurufen.  
  
 Weitere Informationen finden Sie unter [Schnittstellen Attribute](/cpp/windows/attributes/interface-attributes) in der visuellen C++ Referenz Dokumentation.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Bibliotheksdefinition mithilfe des `GUID_ManagedName`-Attributs.  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Cor. h
