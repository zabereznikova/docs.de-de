---
title: IAssemblyName::GetName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134346"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="a6916-102">IAssemblyName::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a6916-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="a6916-103">Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die von diesem [IAssemblyName](iassemblyname-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a6916-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6916-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6916-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6916-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6916-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="a6916-106">[in, out] Die Größe der `pwzName` in breit Zeichen, einschließlich des NULL-Abschluss Zeichens.</span><span class="sxs-lookup"><span data-stu-id="a6916-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="a6916-107">vorgenommen Ein Puffer, der den Namen der Assembly enthalten soll, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a6916-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6916-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6916-108">Requirements</span></span>  
 <span data-ttu-id="a6916-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6916-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6916-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a6916-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a6916-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6916-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6916-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6916-112">See also</span></span>

- [<span data-ttu-id="a6916-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6916-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
