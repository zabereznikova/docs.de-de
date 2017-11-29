---
title: CorSymSearchPolicyAttributes-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="49d55-102">CorSymSearchPolicyAttributes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="49d55-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="49d55-103">Gibt die Richtlinie beim Ausführen einer Suche für einen Symbolreader verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49d55-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="49d55-104">Diese Konstanten werden verwendet, indem Sie die [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) und [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="49d55-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="49d55-105">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="49d55-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d55-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="49d55-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="49d55-107">Member</span><span class="sxs-lookup"><span data-stu-id="49d55-107">Members</span></span>  
  
|<span data-ttu-id="49d55-108">Member</span><span class="sxs-lookup"><span data-stu-id="49d55-108">Member</span></span>|<span data-ttu-id="49d55-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49d55-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="49d55-110">Fragt die Registrierung für Symbolsuchpfaden an.</span><span class="sxs-lookup"><span data-stu-id="49d55-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="49d55-111">Greift auf einen anderen Symbolserver.</span><span class="sxs-lookup"><span data-stu-id="49d55-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="49d55-112">Durchsucht den Pfad in der Debug-Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="49d55-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="49d55-113">Sucht die PDB-Datei an der Stelle, wo die .exe-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="49d55-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49d55-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49d55-114">Requirements</span></span>  
 <span data-ttu-id="49d55-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49d55-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d55-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d55-116">See Also</span></span>  
 [<span data-ttu-id="49d55-117">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="49d55-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
