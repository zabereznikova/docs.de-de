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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4da0e064f507e2330aac27fc5c8bcd56b9d3c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716231"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="d2ad0-102">CREATE_ASM_NAME_OBJ_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2ad0-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="d2ad0-103">Gibt die Attribute einer [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) -Objekt nach der Erstellung durch die [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ad0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2ad0-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d2ad0-105">Member</span><span class="sxs-lookup"><span data-stu-id="d2ad0-105">Members</span></span>  
  
|<span data-ttu-id="d2ad0-106">Member</span><span class="sxs-lookup"><span data-stu-id="d2ad0-106">Member</span></span>|<span data-ttu-id="d2ad0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2ad0-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="d2ad0-108">Gibt an, dass der übergebene Parameter eine Text Identität ist.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="d2ad0-109">Einige Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="d2ad0-110">Überprüft die Friend-Assembly-Regel (nur Name und öffentlicher Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="d2ad0-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="d2ad0-111">Dieser Member ist nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="d2ad0-112">Eine Kombination aus den `CANOF_PARSE_DISPLAY_NAME` und `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` Flags.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="d2ad0-113">Dieser Member ist nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d2ad0-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2ad0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2ad0-114">Requirements</span></span>  
 <span data-ttu-id="d2ad0-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2ad0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2ad0-116">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d2ad0-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d2ad0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2ad0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ad0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ad0-118">See also</span></span>
- [<span data-ttu-id="d2ad0-119">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2ad0-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="d2ad0-120">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="d2ad0-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="d2ad0-121">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d2ad0-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
