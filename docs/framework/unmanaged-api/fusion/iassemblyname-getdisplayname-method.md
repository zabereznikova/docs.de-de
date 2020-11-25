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
ms.openlocfilehash: 13d71a9da2539c45076e5eb92e153e37c1df4b47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727912"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="0df2b-102">IAssemblyName::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="0df2b-102">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="0df2b-103">Ruft den lesbaren Namen der Assembly ab, auf die von diesem [IAssemblyName](iassemblyname-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0df2b-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0df2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0df2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0df2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0df2b-105">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="0df2b-106">vorgenommen Der Zeichen folgen Puffer, der den Namen der Assembly enthält, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0df2b-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="0df2b-107">[in, out] Die Größe von `szDisplayName` in breit Zeichen, einschließlich eines NULL-Abschluss Zeichens.</span><span class="sxs-lookup"><span data-stu-id="0df2b-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="0df2b-108">in Eine bitweise Kombination von [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) -Werten, die die Funktionen von beeinflussen `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="0df2b-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0df2b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0df2b-109">Requirements</span></span>  

 <span data-ttu-id="0df2b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0df2b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0df2b-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0df2b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0df2b-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0df2b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df2b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0df2b-113">See also</span></span>

- [<span data-ttu-id="0df2b-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0df2b-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="0df2b-115">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="0df2b-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
