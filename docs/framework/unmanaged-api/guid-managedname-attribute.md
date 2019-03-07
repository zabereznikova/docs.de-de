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
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496390"
---
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="f1aa6-102">GUID_ManagedName-Attribut</span><span class="sxs-lookup"><span data-stu-id="f1aa6-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="f1aa6-103">Definiert eine benutzerdefinierte Schnittstelle-Attribut, das Namen des verwalteten Namespaces für eine Komponente Objekt Model (COM)-Bibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1aa6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1aa6-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1aa6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1aa6-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="f1aa6-106">Der verwaltete Namespace-Name für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="f1aa6-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f1aa6-107">Definition</span></span>  
 <span data-ttu-id="f1aa6-108">`GUID_ManagedName` wird in Cor.h wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="f1aa6-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f1aa6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1aa6-109">Remarks</span></span>  
 <span data-ttu-id="f1aa6-110">Eine benutzerdefinierte Schnittstelle-Attribut definiert die Metadaten für ein Objekt in der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="f1aa6-111">Verwendung <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> der verwaltete Name des Attributs abrufen.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="f1aa6-112">Weitere Informationen finden Sie unter [Schnittstellenattribute](/cpp/windows/interface-attributes) in Visual C++-Referenzdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1aa6-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1aa6-113">Example</span></span>  
 <span data-ttu-id="f1aa6-114">Das folgende Beispiel zeigt eine Bibliothek mit den `GUID_ManagedName` Attribut.</span><span class="sxs-lookup"><span data-stu-id="f1aa6-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="f1aa6-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1aa6-115">Requirements</span></span>  
 <span data-ttu-id="f1aa6-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1aa6-116">**Header:** Cor.h</span></span>
