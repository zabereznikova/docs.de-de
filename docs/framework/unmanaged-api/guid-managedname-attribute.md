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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bae50f695de81856d4fddcb2af3d1188d896642
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430010"
---
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="03da1-102">GUID_ManagedName-Attribut</span><span class="sxs-lookup"><span data-stu-id="03da1-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="03da1-103">Definiert eine benutzerdefinierte Schnittstelle-Attribut, das Namen des verwalteten Namespaces für eine Komponente-Objektbibliothek Model (COM) angibt.</span><span class="sxs-lookup"><span data-stu-id="03da1-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03da1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03da1-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03da1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="03da1-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="03da1-106">Der Name der verwalteten Namespace für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="03da1-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="03da1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="03da1-107">Definition</span></span>  
 <span data-ttu-id="03da1-108">`GUID_ManagedName` wird in Cor.h wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="03da1-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="03da1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03da1-109">Remarks</span></span>  
 <span data-ttu-id="03da1-110">Ein Attribut für die benutzerdefinierte Schnittstelle definiert die Metadaten für ein Objekt in der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="03da1-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="03da1-111">Verwendung <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> zum Abrufen der verwaltete Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="03da1-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="03da1-112">Weitere Informationen finden Sie unter [Schnittstellenattribute](/cpp/windows/interface-attributes) in der Visual C++-Referenzdokumentation.</span><span class="sxs-lookup"><span data-stu-id="03da1-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03da1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03da1-113">Example</span></span>  
 <span data-ttu-id="03da1-114">Das folgende Beispiel zeigt eine Bibliothek mit den `GUID_ManagedName` Attribut.</span><span class="sxs-lookup"><span data-stu-id="03da1-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="03da1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03da1-115">Requirements</span></span>  
 <span data-ttu-id="03da1-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03da1-116">**Header:** Cor.h</span></span>
