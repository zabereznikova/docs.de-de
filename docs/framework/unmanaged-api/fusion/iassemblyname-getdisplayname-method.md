---
title: IAssemblyName::GetDisplayName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f48f2d95829d2c8111065e5f4ede4e43a16d63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796652"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="2e488-102">IAssemblyName::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="2e488-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="2e488-103">Ruft den lesbaren Namen der Assembly ab, auf die von diesem [IAssemblyName](iassemblyname-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2e488-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e488-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e488-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e488-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e488-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="2e488-106">vorgenommen Der Zeichen folgen Puffer, der den Namen der Assembly enthält, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2e488-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="2e488-107">[in, out] Die Größe von `szDisplayName` in breit Zeichen, einschließlich eines NULL-Abschluss Zeichens.</span><span class="sxs-lookup"><span data-stu-id="2e488-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="2e488-108">in Eine bitweise Kombination von [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) -Werten, die sich auf `szDisplayName`die Funktionen von auswirken.</span><span class="sxs-lookup"><span data-stu-id="2e488-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e488-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e488-109">Requirements</span></span>  
 <span data-ttu-id="2e488-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e488-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e488-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2e488-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2e488-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e488-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e488-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e488-113">See also</span></span>

- [<span data-ttu-id="2e488-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e488-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2e488-115">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2e488-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
