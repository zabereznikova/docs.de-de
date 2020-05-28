---
title: CorMethodAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 779a8f88b7521aa4b0a75594552981b41714ee3f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007675"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="43efe-102">CorMethodAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="43efe-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="43efe-103">Enthält Werte, die die Funktionen einer Methode beschreiben.</span><span class="sxs-lookup"><span data-stu-id="43efe-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43efe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43efe-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="43efe-105">Member</span><span class="sxs-lookup"><span data-stu-id="43efe-105">Members</span></span>  
  
|<span data-ttu-id="43efe-106">Member</span><span class="sxs-lookup"><span data-stu-id="43efe-106">Member</span></span>|<span data-ttu-id="43efe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43efe-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="43efe-108">Gibt den Element Zugriff an.</span><span class="sxs-lookup"><span data-stu-id="43efe-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="43efe-109">Gibt an, dass auf den Member nicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="43efe-110">Gibt an, dass der Zugriff auf den Member nur über den übergeordneten Typ möglich ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="43efe-111">Gibt an, dass nur Untertypen in dieser Assembly auf den Member zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="43efe-112">Gibt an, dass der Member von allen Personen in der Assembly zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="43efe-113">Gibt an, dass auf den Member nur nach Typ und Untertypen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="43efe-114">Gibt an, dass auf den Member durch abgeleitete Klassen und andere Typen in der Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="43efe-115">Gibt an, dass der Zugriff auf den Member für alle Typen mit Zugriff auf den Bereich möglich ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="43efe-116">Gibt an, dass der Member als Teil des Typs und nicht als Member einer Instanz definiert wird.</span><span class="sxs-lookup"><span data-stu-id="43efe-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="43efe-117">Gibt an, dass die Methode nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="43efe-118">Gibt an, dass die Methode überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="43efe-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="43efe-119">Gibt an, dass die Methode nach Name und Signatur und nicht nur nach Namen ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="43efe-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="43efe-120">Gibt das Layout der virtuellen Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="43efe-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="43efe-121">Gibt an, dass der für diese Methode in der virtuellen Tabelle verwendete Slot wieder verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43efe-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="43efe-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="43efe-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="43efe-123">Gibt an, dass die Methode immer einen neuen Slot in der virtuellen Tabelle erhält.</span><span class="sxs-lookup"><span data-stu-id="43efe-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="43efe-124">Gibt an, dass die Methode von denselben Typen überschrieben werden kann, auf die Sie sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="43efe-125">Gibt an, dass die Methode nicht implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="43efe-126">Gibt an, dass die Methode speziell ist, und dass Ihr Name beschreibt, wie.</span><span class="sxs-lookup"><span data-stu-id="43efe-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="43efe-127">Gibt an, dass die Methoden Implementierung mithilfe von PInvoke weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="43efe-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="43efe-128">Gibt an, dass die Methode eine verwaltete Methode ist, die in nicht verwalteten Code exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="43efe-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="43efe-129">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="43efe-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="43efe-130">Gibt an, dass die Common Language Runtime die Codierung des Methoden namens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="43efe-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="43efe-131">Gibt an, dass der Methode Sicherheit zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="43efe-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="43efe-132">Gibt an, dass die Methode eine andere Methode aufruft, die Sicherheitscode enthält.</span><span class="sxs-lookup"><span data-stu-id="43efe-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43efe-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43efe-133">Requirements</span></span>  
 <span data-ttu-id="43efe-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43efe-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43efe-135">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="43efe-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="43efe-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43efe-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43efe-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43efe-137">See also</span></span>

- [<span data-ttu-id="43efe-138">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="43efe-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
