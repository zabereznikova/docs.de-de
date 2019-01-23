---
title: CorSymSearchPolicyAttributes-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ed868febb5eb82cf73cfc5b0633d86bf4e1315c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561620"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="fe6bc-102">CorSymSearchPolicyAttributes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fe6bc-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="fe6bc-103">Gibt die Richtlinie beim Ausführen einer Suche für einen Symbolreader verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="fe6bc-104">Diese Konstanten werden verwendet, durch die [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) und [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe6bc-105">Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6bc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe6bc-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="fe6bc-107">Member</span><span class="sxs-lookup"><span data-stu-id="fe6bc-107">Members</span></span>  
  
|<span data-ttu-id="fe6bc-108">Member</span><span class="sxs-lookup"><span data-stu-id="fe6bc-108">Member</span></span>|<span data-ttu-id="fe6bc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe6bc-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="fe6bc-110">Fragt die Registrierung für die Symbolsuchpfade an.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="fe6bc-111">Greift auf einen anderen Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="fe6bc-112">Durchsucht den Pfad in das Debugverzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="fe6bc-113">Sucht die PDB-Datei an der Stelle, wo die .exe-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="fe6bc-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe6bc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe6bc-114">Requirements</span></span>  
 <span data-ttu-id="fe6bc-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fe6bc-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6bc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe6bc-116">See also</span></span>
- [<span data-ttu-id="fe6bc-117">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fe6bc-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
