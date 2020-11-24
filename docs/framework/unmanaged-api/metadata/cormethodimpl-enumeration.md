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
ms.openlocfilehash: 40e82997e58292a10f5e960cc9d9785d9ea8946a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676971"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="aa1c3-102">CorMethodImpl-Enumeration</span><span class="sxs-lookup"><span data-stu-id="aa1c3-102">CorMethodImpl Enumeration</span></span>

<span data-ttu-id="aa1c3-103">Enthält Werte, die Funktionen zur Implementierung von Methoden beschreiben.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa1c3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="aa1c3-105">Member</span><span class="sxs-lookup"><span data-stu-id="aa1c3-105">Members</span></span>  
  
|<span data-ttu-id="aa1c3-106">Member</span><span class="sxs-lookup"><span data-stu-id="aa1c3-106">Member</span></span>|<span data-ttu-id="aa1c3-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa1c3-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="aa1c3-108">Flags, die den Codetyp beschreiben.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="aa1c3-109">Gibt an, dass die Methoden Implementierung Microsoft Intermediate Language (MSIL) ist.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="aa1c3-110">Gibt an, dass die Methodenimplementierung nativ ist.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="aa1c3-111">Gibt an, dass die Methoden Implementierung OPTIL ist.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="aa1c3-112">Gibt an, dass die Methoden Implementierung vom Common Language Runtime bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="aa1c3-113">Flags, die angeben, ob der Code verwaltet oder nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="aa1c3-114">Gibt an, dass die Methoden Implementierung nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="aa1c3-115">Gibt an, dass die Methoden Implementierung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="aa1c3-116">Gibt an, dass die-Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-116">Specifies that the method is defined.</span></span> <span data-ttu-id="aa1c3-117">Dieses Flag wird primär in zusammenlaufverfolgungsszenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="aa1c3-118">Gibt an, dass die Methoden Signatur für eine HRESULT-Konvertierung nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="aa1c3-119">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="aa1c3-120">Gibt an, dass die Methode einen Single Thread durch Ihren Text enthält.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="aa1c3-121">Gibt an, dass die Methode nicht intern sein kann.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="aa1c3-122">Gibt an, dass die Methode nach Möglichkeit Inline sein soll.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="aa1c3-123">Gibt an, dass die Methode nicht optimiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa1c3-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="aa1c3-124">Der Höchstwert für einen `CorMethodImpl` .</span><span class="sxs-lookup"><span data-stu-id="aa1c3-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa1c3-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa1c3-125">Requirements</span></span>  

 <span data-ttu-id="aa1c3-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa1c3-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa1c3-127">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="aa1c3-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="aa1c3-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa1c3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1c3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa1c3-129">See also</span></span>

- [<span data-ttu-id="aa1c3-130">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="aa1c3-130">Metadata Enumerations</span></span>](metadata-enumerations.md)
