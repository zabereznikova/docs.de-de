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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 249de91483117db6b497fa8eae6f97c3eb0a0587
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045525"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="8ffb1-102">CorMethodAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8ffb1-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="8ffb1-103">Enthält Werte, die die Funktionen einer Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ffb1-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="8ffb1-105">Member</span><span class="sxs-lookup"><span data-stu-id="8ffb1-105">Members</span></span>  
  
|<span data-ttu-id="8ffb1-106">Member</span><span class="sxs-lookup"><span data-stu-id="8ffb1-106">Member</span></span>|<span data-ttu-id="8ffb1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ffb1-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="8ffb1-108">Gibt den Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="8ffb1-109">Gibt an, dass der Member nicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="8ffb1-110">Gibt an, dass der Member nur von den übergeordneten Typ zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="8ffb1-111">Gibt an, dass der Member von Untertypen in dieser Assembly nur zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="8ffb1-112">Gibt an, dass der Member Zugriff von jedem Benutzer in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="8ffb1-113">Gibt an, dass der Member nur von Typen und Untertypen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="8ffb1-114">Gibt an, dass der Member von abgeleiteten Klassen und andere Typen in der Assembly verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="8ffb1-115">Gibt an, dass der Member von allen Typen mit Zugriff auf den Bereich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="8ffb1-116">Gibt an, dass der Member nicht als Mitglied einer Instanz, sondern als Teil des Typs definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="8ffb1-117">Gibt an, dass die Methode nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="8ffb1-118">Gibt an, dass die Methode überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="8ffb1-119">Gibt an, dass die Methode durch den Namen und derselben Signatur und nicht nur durch den Namen verbirgt.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="8ffb1-120">Gibt die virtuellen Tabellenlayout.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="8ffb1-121">Gibt an, dass der Slot für diese Methode in der virtuellen Tabelle verwendete wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="8ffb1-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="8ffb1-123">Gibt an, dass die Methode immer einen neuen Slot in der virtuellen Tabelle abruft.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="8ffb1-124">Gibt an, dass die Methode von den Typen überschrieben werden kann, zu dem es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="8ffb1-125">Gibt an, dass die Methode nicht implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="8ffb1-126">Gibt an, dass besondere Methode handelt und der Name wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="8ffb1-127">Gibt an, dass die methodenimplementierung mit PInvoke weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="8ffb1-128">Gibt an, dass die Methode eine verwaltete Methode, die in nicht verwaltetem Code exportiert.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="8ffb1-129">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="8ffb1-130">Gibt an, dass die common Language Runtime die Codierung des Methodennamens überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="8ffb1-131">Gibt an, dass die Methode Sicherheitsfunktionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="8ffb1-132">Gibt an, dass die Methode, eine andere Methode aufruft, die Sicherheitscode enthält.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ffb1-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ffb1-133">Requirements</span></span>  
 <span data-ttu-id="8ffb1-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb1-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ffb1-135">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8ffb1-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8ffb1-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ffb1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ffb1-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ffb1-137">See also</span></span>

- [<span data-ttu-id="8ffb1-138">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="8ffb1-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
