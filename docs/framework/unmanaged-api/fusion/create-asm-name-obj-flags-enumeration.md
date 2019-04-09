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
ms.openlocfilehash: aebc6dfe4830e6477cda8fd279b8ef2a8040895c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149668"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="e8f60-102">CREATE_ASM_NAME_OBJ_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e8f60-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="e8f60-103">Gibt die Attribute einer [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) -Objekt nach der Erstellung durch die [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e8f60-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8f60-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e8f60-105">Member</span><span class="sxs-lookup"><span data-stu-id="e8f60-105">Members</span></span>  
  
|<span data-ttu-id="e8f60-106">Member</span><span class="sxs-lookup"><span data-stu-id="e8f60-106">Member</span></span>|<span data-ttu-id="e8f60-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8f60-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="e8f60-108">Gibt an, dass der übergebene Parameter eine Text Identität ist.</span><span class="sxs-lookup"><span data-stu-id="e8f60-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="e8f60-109">Einige Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e8f60-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="e8f60-110">Überprüft die Friend-Assembly-Regel (nur Name und öffentlicher Schlüssel).</span><span class="sxs-lookup"><span data-stu-id="e8f60-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="e8f60-111">Dieser Member ist nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e8f60-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="e8f60-112">Eine Kombination aus den `CANOF_PARSE_DISPLAY_NAME` und `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` Flags.</span><span class="sxs-lookup"><span data-stu-id="e8f60-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="e8f60-113">Dieser Member ist nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e8f60-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8f60-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8f60-114">Requirements</span></span>  
 <span data-ttu-id="e8f60-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f60-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f60-116">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e8f60-116">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="e8f60-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e8f60-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8f60-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8f60-118">See also</span></span>

- [<span data-ttu-id="e8f60-119">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8f60-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e8f60-120">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="e8f60-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="e8f60-121">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="e8f60-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
