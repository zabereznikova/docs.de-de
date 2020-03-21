---
title: SetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179387"
---
# <a name="setpekind-method"></a><span data-ttu-id="d0658-102">SetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="d0658-102">SetPEKind Method</span></span>
<span data-ttu-id="d0658-103">Bestimmt den portablen ausführbaren Typ, entweder maschinenspezifisch oder maschinenunabhängig.</span><span class="sxs-lookup"><span data-stu-id="d0658-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0658-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0658-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="d0658-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0658-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d0658-106">ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d0658-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d0658-107">Token der Datei, für die der PE-Typ festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0658-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="d0658-108">Kann NULL `AssemblyID` sein, wenn es nicht auf ein ungebundenes Netmodule hinweist.</span><span class="sxs-lookup"><span data-stu-id="d0658-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="d0658-109">Der Pe-Typ, wie durch die [CorPEKind-Enumeration](../metadata/corpekind-enumeration.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="d0658-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="d0658-110">Die Zielcomputerarchitektur, wie im NT-Header angegeben.</span><span class="sxs-lookup"><span data-stu-id="d0658-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0658-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0658-111">Return Value</span></span>  
 <span data-ttu-id="d0658-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d0658-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0658-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0658-113">Requirements</span></span>  
 <span data-ttu-id="d0658-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="d0658-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0658-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0658-115">See also</span></span>

- [<span data-ttu-id="d0658-116">GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="d0658-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="d0658-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0658-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d0658-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0658-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d0658-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="d0658-119">ALink API</span></span>](index.md)
