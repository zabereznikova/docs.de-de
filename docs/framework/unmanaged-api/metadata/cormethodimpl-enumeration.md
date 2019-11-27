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
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="9ba42-102">CorMethodImpl-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9ba42-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="9ba42-103">Enthält Werte, die Funktionen zur Implementierung von Methoden beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9ba42-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ba42-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9ba42-105">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="9ba42-105">Members</span></span>  
  
|<span data-ttu-id="9ba42-106">Member</span><span class="sxs-lookup"><span data-stu-id="9ba42-106">Member</span></span>|<span data-ttu-id="9ba42-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ba42-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="9ba42-108">Flags, die den Codetyp beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9ba42-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="9ba42-109">Gibt an, dass die Methoden Implementierung Microsoft Intermediate Language (MSIL) ist.</span><span class="sxs-lookup"><span data-stu-id="9ba42-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="9ba42-110">Gibt an, dass die Methodenimplementierung nativ ist.</span><span class="sxs-lookup"><span data-stu-id="9ba42-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="9ba42-111">Gibt an, dass die Methoden Implementierung OPTIL ist.</span><span class="sxs-lookup"><span data-stu-id="9ba42-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="9ba42-112">Gibt an, dass die Methoden Implementierung vom Common Language Runtime bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9ba42-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="9ba42-113">Flags, die angeben, ob der Code verwaltet oder nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9ba42-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="9ba42-114">Gibt an, dass die Methoden Implementierung nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9ba42-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="9ba42-115">Gibt an, dass die Methoden Implementierung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9ba42-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="9ba42-116">Gibt an, dass die-Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="9ba42-116">Specifies that the method is defined.</span></span> <span data-ttu-id="9ba42-117">Dieses Flag wird primär in zusammenlaufverfolgungsszenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ba42-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="9ba42-118">Gibt an, dass die Methoden Signatur für eine HRESULT-Konvertierung nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ba42-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="9ba42-119">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9ba42-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="9ba42-120">Gibt an, dass die Methode einen Single Thread durch Ihren Text enthält.</span><span class="sxs-lookup"><span data-stu-id="9ba42-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="9ba42-121">Gibt an, dass die Methode nicht intern sein kann.</span><span class="sxs-lookup"><span data-stu-id="9ba42-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="9ba42-122">Gibt an, dass die Methode nach Möglichkeit Inline sein soll.</span><span class="sxs-lookup"><span data-stu-id="9ba42-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="9ba42-123">Gibt an, dass die Methode nicht optimiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba42-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="9ba42-124">Der Höchstwert für einen `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="9ba42-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ba42-125">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9ba42-125">Requirements</span></span>  
 <span data-ttu-id="9ba42-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba42-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba42-127">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="9ba42-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9ba42-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba42-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba42-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ba42-129">See also</span></span>

- [<span data-ttu-id="9ba42-130">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9ba42-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
