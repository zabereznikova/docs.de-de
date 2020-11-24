---
title: CREATE_ASM_NAME_OBJ_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: 52d5ad3a18c102422e90621c7d1e23b2692c0000
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683230"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="017c7-102">CREATE_ASM_NAME_OBJ_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="017c7-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>

<span data-ttu-id="017c7-103">Gibt die Attribute eines [IAssemblyName-Schnittstellen](iassemblyname-interface.md) Objekts an, wenn es von der Funktion " [kreateassemblynameobject](createassemblynameobject-function.md) " erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="017c7-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="017c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="017c7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="017c7-105">Member</span><span class="sxs-lookup"><span data-stu-id="017c7-105">Members</span></span>  
  
|<span data-ttu-id="017c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="017c7-106">Member</span></span>|<span data-ttu-id="017c7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="017c7-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="017c7-108">Gibt an, dass der übergebenen Parameter eine Text Identität ist.</span><span class="sxs-lookup"><span data-stu-id="017c7-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="017c7-109">Legt einige Standardwerte fest.</span><span class="sxs-lookup"><span data-stu-id="017c7-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="017c7-110">Überprüft die Friend-Assemblyregel (nur Name und öffentlicher Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="017c7-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="017c7-111">Dieser Member ist nur für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="017c7-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="017c7-112">Eine Kombination der `CANOF_PARSE_DISPLAY_NAME` -und- `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` Flags.</span><span class="sxs-lookup"><span data-stu-id="017c7-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="017c7-113">Dieser Member ist nur für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="017c7-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="017c7-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="017c7-114">Requirements</span></span>  

 <span data-ttu-id="017c7-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="017c7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="017c7-116">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="017c7-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="017c7-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="017c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017c7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="017c7-118">See also</span></span>

- [<span data-ttu-id="017c7-119">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="017c7-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="017c7-120">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="017c7-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="017c7-121">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="017c7-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
